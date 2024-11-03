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

 `|sc roc paper|
sc := Scissors new.
roc := Rock new.
paper :=Paper new.
Transcript show: (roc vs: paper ).```
aprés dans chaque classe on personnaliser les methode :
```
playagainstScissors 
^ #scissors
playagainstPaper 
 #nulle 
playagainstPaper 
 #nulle ```
## avancement Kata 
je suis en trains d'implementer l'en passant move mais je trouve toujours des difficulté 
j'ai essayer de initialiser la possibilité d'etre capturé en passant à faux 
```
resetEnPassantFlags
    "Réinitialise le drapeau canBeCapturedEnPassant pour tous les pions"
   "Réinitialise le drapeau canBeCapturedEnPassant pour tous les pions sur le plateau"
    | allPawns |
    allPawns := board pieces select: [ :piece | piece id = 'P' ].
    allPawns do: [ :pawn | pawn canBeCapturedEnPassant: false ].```
 ```   
 But de la fonction :

Assurer que, après chaque mouvement, aucun pion sur le plateau n'est indûment marqué comme pouvant être capturé en passant.
Cette réinitialisation est nécessaire car, selon les règles des échecs, un pion n'est vulnérable à la capture en passant que immédiatement après avoir effectué un double pas.

recordMovementOf: aPiece to: aSquare [
	"moves add: (MyMove piece: aPiece square: aSquare name)."

	| prefix movesText moveDistance startSquare | 
	startSquare := aPiece square.
    "aPiece moveTo: aSquare" "Assurez-vous que le déplacement se fait après avoir stocké startSquare"

	prefix := currentPlayer isWhite
		          ifTrue: [ moveCount asString , '.' ] 
		          ifFalse: [ '' ].
	moves add: prefix , ' ' , aPiece id , aSquare name.
	self  resetEnPassantFlags . 
	"Si la pièce est un pion, vérifier s'il a bougé de deux cases"
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
	
	movesLabel text: movesText
]```
Enregistrement du mouvement :
Garde une trace des mouvements effectués pour l'historique de la partie.
Gestion du mouvement "en passant" :
Met à jour le drapeau canBeCapturedEnPassant pour le pion qui vient de se déplacer, si nécessaire.
Mise à jour de l'affichage :
Met à jour l'interface utilisateur pour refléter les mouvements récents.

jusqu'a maintenant la fonctionnalité en pasant ne fonctionne pas ,je suis en trains de deboguer pour savoir le probléme vient d'ou