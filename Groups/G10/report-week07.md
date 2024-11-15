# Rapport semaine n°7 - Groupe 10

## Elsa Logier

### Expérimentation théorique en groupe

Nous trouvant tous bloqués sur le même sujet, (le nombre exponentiel de blocs avec des if dans le projet), nous avons décidé de nous réunir avec Maureen et Thomas afin de réfléchir à la question car, même si nous venons de groupes différents, l'union fait la force et notre mise en commun nous a permis d'avoir des idées

Nous avons trouvé un design nous permettant de réduire considérablement le nombre de blocs de condition **ainsi que** le nombre de duplications de code nécessaires afin de faire fonctionner chaque mouvement pour chaque pièce
Evidemment, même si notre Kata commun porte sur les mouvements des pions, il reste important à mon sens de garder en tête l'amélioration du projet au global et laisser ouvert les possibilités d'amélioration afin de faire coller ce projet un maximum aux conditions réelles de développement 


### Mise en place de la solution proposée

J'ai commencé par créer deux nouvelles classes MyWhitePawn et MyBlackPawn héritant de MyPawn. 
J'ai ensuite recréé dans chaque classe la méthode targetSquaresLegal
```pharo
MyBlackPawn << targetSquaresLegal: aBoolean

	^ (isFirstMove
		   ifFalse: [ { square down } ]
		   ifTrue: [
			   {
				   square down.
				   self moveTwoDown } ]) select: [ :s |
		  s notNil and: s hasPiece not ]
```

### Problèmes avec Git 

Après m'être assurée que mes modifications étaient fonctionnelles , j'ai essayé de faire un merge sur la branche main.
Malheureusement, des conflits se sont créés car Aymeric avait créé des classes avec les mêmes noms et une méthode à l'intérieur. 

J'ai perdu plus de deux heures et une grande partie de mon travail et j'ai du refaire une nouvelle branche mais finalement tout se termine bien. Mes premiers mouvements de pions sont fonctionnels malgré quelques méthodes en moins qui seront de toute façon recréées autre part plus tard 

## Aymeric Jakobowski

### Réalisé en cours

J'ai beaucoup avancé sur mon kata, j'ai donc commencé à implémenter le double dispatch. Vous pouvez par ailleurs retrouver quelques de mes commits sur cette page : https://github.com/AymericJak/chess-group-10/pull/4/commits

Nous avons avec plusieurs groupes (les personnes qui réalisent la même mission que moi) comparé nos différentes implémentations. C'est assez drôle de voir que nous avons chacun une implémentation différente de la chose.

### Réalisé à la maison

- J'ai regardé le slide sur le composite : [Composite: a Nice and Common Design Pattern](http://rmod-pharo-mooc.lille.inria.fr/AdvancedDesignMooc/Slides/M5-1-DesignPattern-03-Composite.pdf)
- J'ai réalisé une Pull Request afin que ma binôme Elsa puisse également avoir le code que j'ai réalisé. Donc son implémentation, l'architecture du projet est similaire à la mienne (création de 2 sous classes pour chaque pièces : par exemple `MyBlackPawn` et `MyWhitePawn`)
