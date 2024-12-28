# Karim EL JISR 

## Polymorphisme, Évolution Logicielle et Recherche de Méthodes
Le polymorphisme est essentiel pour permettre l'évolution logicielle en rendant les objets interchangeables sans modifier le code existant. En langages dynamiquement typés, comme Pharo, le "duck typing" permet cette flexibilité naturellement : un objet peut jouer un rôle s’il comprend les méthodes nécessaires. Dans les langages statiquement typés, comme Java, les interfaces offrent une solution en définissant des contrats indépendants des hiérarchies de classes, facilitant l’ajout de nouvelles fonctionnalités sans altérer les structures existantes.

La recherche de méthodes repose sur le type dynamique d’un objet. Lorsqu’un message est envoyé, le système identifie la classe de l’objet, puis remonte sa hiérarchie pour trouver la méthode correspondante. Ce mécanisme garantit flexibilité et modularité, surtout dans un contexte polymorphe, en alignant le comportement avec le type réel de l’objet et non son type déclaré. En somme, le polymorphisme et la recherche de méthodes sont des outils clés pour concevoir des systèmes évolutifs et robustes. 


# MOULOUEL Tarik 

## TYPAGES STATIQUE ET DYNAMIQUE : 
 - Dans un langage à typage statique  : Les types sont vérifiés à la compilation. Cela signifie que le compilateur a besoin de connaître à l’avance le type exact de chaque variable ou paramètr 
 - Dans un langage à typage dynamique :
Les types ne sont vérifiés qu’à l’exécution. Concrètement, une variable peut changer de type au cours du programme. 

- Les objets polymorphes : un facteur clé pour l’évolution d’un logiciel Le polymorphisme désigne la capacité à appeler la même méthode ou fonction sur différents types d’objets, tout en obtenant un comportement spécifique à chaque type. Cette flexibilité est cruciale pour faire évoluer un logiciel sans nécessiter de réécriture massive. En effet, on peut ainsi ajouter de nouvelles fonctionnalités ou de nouveaux types d’objets tout en conservant le même code client.

- Le patron de conception Adapter illustre très bien le principe du polymorphisme : en créant un adaptateur qui fait le lien entre une classe existante et une interface cible, on rend les deux compatibles sans modifier la classe initiale. Cela montre comment on peut exploiter le polymorphisme pour adapter des composants hétérogènes, tout en maintenant une structure claire et évolutive.
# Mohamed yassine aloui section
## TYPAGES 
Dans un langage à typage statique, les types sont vérifiés à la compilation ; dans un langage à typage dynamique, ils le sont à l’exécution.
Le polymorphisme permet d’appeler la même méthode sur différents types d’objets, favorisant ainsi l’évolution logicielle sans réécriture massive.
Le patron Adapter illustre cette flexibilité en rendant compatibles des composants hétérogènes, sans modifier la classe initiale.
#avancement de kata fix pawn moves
## j'ai implémenté tpus les fonctionnalité de mypawn à part la fonctionnalité d'enpassant 
## Méthode resetEnPassantFlags

```resetEnPassantFlags
    "Réinitialise le drapeau canBeCapturedEnPassant pour tous les pions sur le plateau"
    | allPawns |
    allPawns := board pieces select: [ :piece | piece id = 'P' ].
    allPawns do: [ :pawn | pawn canBeCapturedEnPassant: false ].

    But : faire en sorte que les pions ne soient vulnérables à la capture en passant que immédiatement après leur double pas.
    Après chaque coup, on met le drapeau à false pour tous.```

## Méthode recordMovementOf:to:

recordMovementOf: aPiece to: aSquare [
    | prefix movesText moveDistance startSquare oldSquare |
    startSquare := aPiece square.  "on stocke la case d'origine avant le déplacement"
    
    prefix := currentPlayer isWhite
              ifTrue: [ moveCount asString , '.' ] 
              ifFalse: [ '' ].
    moves add: prefix , ' ' , aPiece id , aSquare name.

    oldSquare := aPiece square.   "Ancienne position"
    self resetEnPassantFlags.

    (aPiece id = 'P') ifTrue: [
        "Nouveau calcul du 'moveDistance' entre file d'origine et file de destination (en termes de rang 1..8)"
        moveDistance := (oldSquare file asInteger - aSquare file asInteger) abs.
        (aPiece isInInitialPosition and: [ moveDistance = 2 ])
            ifTrue: [ aPiece canBeCapturedEnPassant: true ]
            ifFalse: [ aPiece canBeCapturedEnPassant: false ].
    ].

    "Mise à jour de l'affichage"
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
] ```

    But :
        Conserver l’historique des mouvements pour l’affichage.
        Réinitialiser l’état canBeCapturedEnPassant de tous les pions.
        Si c’est un pion qui bouge, calculer la distance en nombre de rangs : s’il a bougé de deux rangs (et était en position initiale), alors on met canBeCapturedEnPassant: true.

## Problème restant : la capture en passant ne fonctionne pas

Malgré ces ajustements (notamment le calcul de la distance moveDistance désormais basé sur la différence file asInteger), la fonctionnalité en passant ne se déclenche pas encore correctement. Je soupçonne :

    Soit un souci dans la méthode moveTo: du pion, qui n’enlève pas l’adversaire lors d’une capture en passant.
    Soit un problème de détection du coup en passant lors du choix du targetSquaresLegal:.
    Ou encore l’ordre d’appel : on vérifie/leve canBeCapturedEnPassant trop tôt ou trop tard.
il faux implementer la logique move to: pour qu'elle gere l'enpassant , du coup il faux utiliser le polymorphisme de l'heritage 
Je suis en train de déboguer cette partie. Pour l’instant, je sais que la mise à jour du drapeau canBeCapturedEnPassant est correcte (on l’a vérifiée). Il me reste donc à vérifier :

    La sélection de la case dans targetSquaresLegal: pour un coup en diagonale sur une case vide.
    Le retrait effectif du pion capturé (celui qui vient de faire un double pas) dans la méthode du pion attaquant.



