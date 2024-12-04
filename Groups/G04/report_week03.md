## PAWLOWSKI Florine 

### lectures :
points importants : 
  - Les objets sont plus que de simples structures de données, il faut comprendre le service qu'ils offrent et leur logique doit être réutilisable.
  - Il faut Eviter les variables globales et les Singleton, c'est difficile à tester, pas assez modulable.Comment gérer les évolutions avec une unique instance ?

### KATA
J'ai choisi de travailler le kata "Refactor piece rendering (practice refactorings, double dispatch and table dispatch)". 
Pour cela j'ai commencé par pratiquer le reverse engineering en analysant de plus près le projet Chess. 

Un point important pour ce kata : "Qu'est ce que le refactoring"
- Changer l'implémentation SANS changer le comportement.
- Améliorer la qualité du code.
- Les tests nous permettent de garantir que notre refactoring est bon.
- Le code coverage est important.

Mon plan pour ce kata est d'abord d'étudier le projet, analyser ce qui me semble pertinant pour le projet (ici surtout les blocks conditionnels), ensuite créer des tests sur l'existant. Créer un UML de classe pour le dispatch et enfin développer les classes et méthodes nécessaires. 
  
- J'ai commencé par regarder la classe MyChessBoard, qui n'a pas de commentaire de classe. Elle permet d'initialiser un Board, les squares, les pièces sur le plateau, mettre en couleur les squares, cliquer sur une case et set un jeu. 
Rien de très intéressant pour mon objectif. 

- Ensuite j'ai parcouru MyChessGame, qui possède un exemple de jeu dans le commentaire de classe. La méthode CheckForMate semble avoir des erreurs. 
Les méthodes initializeFromFENGame, play et recordMovementOf ont toutes les trois des blocks de conditions ifTrue: , ifFalse: basé à priori sur la couleur du joueur/des cases (exemple de condition : currentPlayer isWhite ou currentPlayer = whitePlayer). 
C'est intéressant, ça veut dire que je pourrais probablement utiliser le dispatch pour éviter ces conditions. 

- Dans MyChessSquare, on retrouve la méthode contents: qui possède un double bloc conditionnel ifNil: ifNotNil: et ifFalse: ifTrue, basé sur la couleur d'une piece (isBlack) 
- méthode foreground : block conditionnel sur isBlack

- Ensuite je suis tombée sur des méthodes intéressantes comme renderBishop:, renderKing:, renderPawn: etc. Ces méthodes sont toutes similaires avec des doubles blocks conditionnels sur la couleur.

Je me suis ensuite penchée sur les tests, il y'en a déjà quelques uns (13 tests) qui semblent tous fonctionner correctement. 
Toutefois les tests sont sur 3 types de pions différents (le roi, la tour et le fou (bishop)) donc il manque des tests sur tous les autres pions.Il y'a aussi une classe test MyFENTest qui test 2 façons de parser des pièces (en noir ou en blanc) et une façon de parser une chaine de caractères en tableau de chaînes de caractères. 

Je dois donc impérativement mettre en place des tests pour tester le bon comportement du projet avant et après le refactoring. 

J'ai aussi remarqué quelque chose de bizarre dans les méthodes render...: les lettres renvoyées n'ont pas forcément de sens, il y'a toujours une lettre qui correspond à la pièce (R pour Rook, B pour Bishop, K pour King etc etc) mais la deuxième lettre choisie dans chaque méthode ne me dit rien. Je ne sais pas si les lettres ont été choisies aléatoirements 

  ```
renderKing: aPiece

	^ aPiece isWhite
		  ifFalse: [
			  color isBlack
				  ifFalse: [ 'L' ]
				  ifTrue: [ 'l' ] ]
		  ifTrue: [
			  color isBlack
				  ifFalse: [ 'K' ]
				  ifTrue: [ 'k' ] ]
```
Par exemple ici pourquoi 'L'/'l' ? 

Pour mettre en place les tests qui concernent les méthodes "render(nom_de_la_pièce)" j'ai voulu initialiser chaque pièce et les mettre sur une case d'une couleur spécifique. J'ai dû aller voir dans MyChessBoard, la méthode initializePieces pour savoir comment préciser la couleur d'une pièce (ex : MyRook black). Pour les squares on peut utiliser la méthode color: aColor pour préciser la couleur d'une case. 

J'ai créé la classe MyChessSquareTest pour tester tous les comportements de chaque méthode render en fonction des pièces. Voici un exemple de test pour la méthode renderBishop:

lien vers la branche pour mon kata avec les tests : 

https://github.com/EvannLietard/Chess/blob/refactor_piece_rendering/src/Myg-Chess-Tests/MyChessSquareTest.class.st 

```
testRenderBishop 

	| squareTest whiteBishop blackBishop |
	squareTest := MyChessSquare new.
	
	"Test fou blanc sur case blanche"
	whiteBishop := MyBishop white. 
	squareTest color: Color white.
	self assert: (squareTest renderBishop: whiteBishop) equals: 'B'.
	" test identique mais avec renderPieceOn qui décide de la méthode appelée en fonction de la pièce"
	self assert: (whiteBishop renderPieceOn: squareTest ) equals: 'B'.
	
	"Test fou blanc sur case noire"
	squareTest color: Color black.
	self assert: (squareTest renderBishop: whiteBishop) equals: 'b'.
	
	"Test fou noir sur case blanche"
	blackBishop := MyBishop black. 
	squareTest color: Color white.
	self assert: (squareTest renderBishop: blackBishop) equals: 'V'.
	
	"Test fou noir sur case noire"
	squareTest color: Color black.
	self assert: (squareTest renderBishop: blackBishop) equals: 'v'.
```
Les tests fonctionnent ce qui est normal je teste le comportement attendu du projet. Ces tests me serviront plus tard pour voir si mon refactoring est bon alors les tests passeront toujours.


## LIETARD Evann 
### Kata
Vous trouverez le code lié a mon kata à ce lien: https://github.com/EvannLietard/Chess/tree/PawnPromotion
#### Analyse
Ayant choisi le kata lié à la promotion du pion, j'ai d'abord effectué une étude du code qui pouvait m'intéresser.
- Je me suis d'abord penché sur la classe MyPawn, mais les deux méthodes présentes n'avaient pas forcément à voir avec ce qui m'intéressait.
- Je suis donc passé à l'étude de la superclasse MyPiece : les méthodes square et board me permettent d'accéder à mon carré et au plateau à partir de n'importe quelle pièce.
- Je suis alors passé à la classe MyChessSquare : ici, j'ai trouvé plusieurs méthodes qui m'intéressaient, notamment hasPiece, qui sert à vérifier si le carré contient une pièce, et content, qui permet de vérifier quelle pièce est sur le carré.
- Enfin, j'ai étudié la classe MyChessBoard : je me suis rendu compte que je ne pouvais pas créer un plateau avec new, il fallait le faire avec empty, puis effectuer différentes initialisations. De plus, la méthode at:put: me permet de placer une pièce à des coordonnées bien précises.
#### Code
- J'ai alors codé un test pour une méthode qui servirait à remplacer une pièce par une nouvelle pièce, ainsi que la méthode qui permet de faire passer ce test au vert.
- J'ai également codé différents tests ayant pour but de vérifier que le comportement des méthodes déjà écrites correspondait bien à celui attendu.
- J'ai recodé la méthode isWhite ainsi que codé la méthode isBlack pour qu'elles soient plus compréhensibles.
- J'ai essayé de coder une méthode shouldPromote qui aurait pour but de vérifier si la case où se trouve le pion permettrait de le promouvoir. Cependant, mes tests renvoyaient false alors que la promotion devait être possible. Après quelques vérifications avec le Transcript dans les différentes méthodes qui pouvaient poser problème, il s'avère que cela est dû à moveTo: qui ne semble pas effectuer le déplacement demandé. Cette méthode renvoie pour l'instant un booléen, ceci étant temporaire le temps de coder une méthode de choix de type de pièce, que ce soit de manière automatique ou manuelle.
### Video/Cours
Ce que j'ai retenu :
- Que les variables globales et les Singletons sont partagés, qu'ils sont difficiles à tester, et que cela empêche de faire du dispatch.



## LAFALAISE Bethuel
##Extras about language
Write small code examples showing how they work and challenging your understanding. Do they work as expected? How can you get a better understanding on their functionning? Add your examples and answers to the report

For the exercise, I defined a class Person and it’s sublass Student (an example I found on the web, and reproduce in Pharo 12.0). Here are the example of codes I tried.
![image](https://github.com/user-attachments/assets/a96fe2a2-05a5-406b-909e-9b100b96fb3f)
![image](https://github.com/user-attachments/assets/72838278-6ced-4df2-82cc-cafb2c0d9f75)

```
Object << #Person
	slots: { #name . #age };
	package: 'Person'

age
	^ age

age: anAge
	age:= anAge.

name
	^name 

name: aName
	name:= aName.

initialize
	name := 'Unknown'.
   	age := 0.

introduce
    ^ 'Hi, my name is ', name, ' and I am ', age asString, ' years old.'.

Person << #Student
	slots: { #StudentId };
	package: 'Person'

StudentId

	^ StudentId

StudentId: anId

	StudentId := anId.

initialize
    super initialize.
    StudentId := 'Unknown'.
```

On the Playground, I tried those these codes :
```
| person |
person := Person new.
person name: 'Bethuel'.
person age: 24.

person introduce.
```
![image](https://github.com/user-attachments/assets/e8896bd8-f8c3-468c-ab08-49434fb9f748)

As shown, it returns : ‘Hi, my name is Bethuel and I am 24 years old.’

```
| student | 
student := Student new. 
student name: 'Bob'. 
student age: 21. 
student introduce.
```
![image](https://github.com/user-attachments/assets/ce646ec7-2caf-4104-be7d-87ec29967826)

As you can see, the returns is not different from its parent : the class Person.

It is possible to override the ```introduce``` method in Student (not tested yet). Which will be like this:

```
introduce 
	^ super introduce, ' My student ID is ', studentId, '.'. 
```

The results from the previous tests worked as expected. They demonstrate how Pharo's class methods and ```super``` operate in practice.

##Project milestone 1

My kata is “Restrict Legal Moves”. Before I even start working on the kata, I think it's necessary to know more about chess and how to play it, as I've never played it before. I've been watching YouTube videos and asking professional friends about it, and I have some good ideas that will help me get started on the project and be on the same page as everyone else on my team.
However, I've taken a look at the MyKing class as well as the other pieces classes, as they're the ones who'll be putting the King in danger or defending him. 
