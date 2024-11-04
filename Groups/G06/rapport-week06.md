# Mohamed Yassine Aloui Section
aprés lecture des pdf de double dispatch et de design pattern visitor j'ai apris ces definitions :
## Compréhension du Double Dispatch

Le double dispatch est un mécanisme de programmation orientée objet qui permet de choisir la méthode à exécuter en fonction du type de deux objets à l'exécution : le récepteur et l'argument. Contrairement au simple dispatch, où la méthode est déterminée uniquement par le type du récepteur, le double dispatch prend en compte le type de l'argument, ce qui est particulièrement utile pour implémenter des comportements polymorphes sans utiliser de structures conditionnelles complexes.

aprés j'ai appliqué dans pharo le jeu :rocket scissors et paper :

En utilisant le double dispatch, chaque coup (Pierre, Papier ou Ciseaux) peut définir comment il interagit avec les autres coups :

```
paper>>vs: anelement
 ^ anelement playagainstPaper.
Rock>>vs: anelement
 ^ anelement playagainstRock.
Scissors>>vs: anelement
 ^ anelement playagainstScissors.
```
au main de playground :
```
 `|sc roc paper|
sc := Scissors new.
roc := Rock new.
paper :=Paper new.
Transcript show: (roc vs: paper ).```
aprés dans chaque classe on personnaliser les methode :
```
dans la classe paper
```
playagainstScissors 
^ #scissors
playagainstPaper 
 #nulle 
playagainstRock 
 #paper ```
dans la classe rock
```
playagainstScissors 
^ #rock
playagainstPaper 
 #paper 
playagainstRock 
 #nulle ```
 dans la classe scissors
```
playagainstScissors 
^ #nulle
playagainstPaper 
 #scissors 
playagainstRock 
 #rock ```
## avancement Kata 
implementation de deux methode clé :
```
resetEnPassantFlags
    "Réinitialise le drapeau canBeCapturedEnPassant pour tous les pions"
   "Réinitialise le drapeau canBeCapturedEnPassant pour tous les pions sur le plateau"
    | allPawns |
    allPawns := board pieces select: [ :piece | piece id = 'P' ].
    allPawns do: [ :pawn | pawn canBeCapturedEnPassant: false ].```
   
 But de la fonction :

Assurer que, après chaque mouvement, aucun pion sur le plateau n'est indûment marqué comme pouvant être capturé en passant.
Cette réinitialisation est nécessaire car, selon les règles des échecs, un pion n'est vulnérable à la capture en passant que immédiatement après avoir effectué un double pas.

```recordMovementOf: aPiece to: aSquare [
	"moves add: (MyMove piece: aPiece square: aSquare name)."

	| prefix movesText moveDistance startSquare | 
	startSquare := aPiece square.
    "aPiece moveTo: aSquare" "Assurez-vous que le déplacement se fait après avoir stocké startSquare"

	prefix := currentPlayer isWhite
		          ifTrue: [ moveCount asString , '.' ] 
		          ifFalse: [ '' ].
	moves add: prefix , ' ' , aPiece id , aSquare name.
	self  resetEnPassantFlags . 
   (aPiece id = 'P') ifTrue: [
        moveDistance := (startSquare y - aSquare y) abs.
        (aPiece isInInitialPosition and: [ moveDistance = 2 ])
            ifTrue: [ aPiece canBeCapturedEnPassant: true ]
            ifFalse: [ aPiece canBeCapturedEnPassant: false ].
    ].
    

	movesText := String streamContents: [ :stream |
		| currentLine |
		currentLine := ''.
		moves do: [ :m |
			currentLine := currentLine, ' ', m.
			currentLine size > 20 ifTrue: [ 
				stream nextPutAll: currentLine.
				stream cr.
				currentLine := ''.
			]
		].
		stream nextPutAll: currentLine
	].
	
	movesLabel text: movesText]
```

Enregistrement du mouvement :
Garde une trace des mouvements effectués pour l'historique de la partie.
Gestion du mouvement "en passant" :
Met à jour le drapeau canBeCapturedEnPassant pour le pion qui vient de se déplacer, si nécessaire.
Mise à jour de l'affichage :
Met à jour l'interface utilisateur pour refléter les mouvements récents.

jusqu'a maintenant la fonctionnalité en pasant ne fonctionne pas ,je suis en trains de deboguer pour savoir le probléme vient d'ou


# Karim EL JISR

The course on Double Dispatch and the Visitor Design Pattern introduces a crucial concept for resolving method selection when the outcome depends on the runtime type of two objects, rather than just the receiver. This pattern avoids the use of conditionals by leveraging polymorphism to handle interactions cleanly and flexibly. The Rock-Paper-Scissors example illustrates this: each class (Stone, Paper, Scissors) implements a vs: method that sends a second message to the argument, such as playAgainstStone, enabling the right behavior to be dynamically selected.

Key Elements:

	•	Double Dispatch: The mechanism uses two method calls. The first determines the receiver, and the second call on the argument selects the appropriate behavior.
	•	Avoiding Conditionals: The solution relies entirely on message sending, making choices using method dispatch rather than explicit checks.
	•	Example Implementation:
	•	Stone>>vs: dispatches to the method playAgainstStone on the argument.
	•	Each class defines methods like playAgainstStone, playAgainstPaper, and playAgainstScissors to determine the result.


The *Visitor Design Pattern* utilizes double dispatch to separate algorithms from the objects they operate on, enabling the addition of new operations without altering existing object structures. This is achieved by having elements accept a "visitor" and call the appropriate method on the visitor, leveraging double dispatch to ensure the correct operation is executed based on the element and visitor types. This pattern enhances modularity, adhering to the Open/Closed Principle by allowing easy addition of new operations while keeping the code maintainable and flexible. It is particularly useful for traversing complex structures like trees, where operations can vary depending on the type of element encountered.

