# Rapport semaine n°9 - Groupe 10

## Elsa Logier



## Aymeric Jakobowski

### Réalisé en cours

- Présentation orale sur le kata « Refactor piece 
rendering » : [group-10-katas-presentation.pdf](documents/group-10-katas-presentation.pdf)
- Suivi des autres présentations, j'ai trouvé intéréssant que pour un même kata, nous sommes nombreux à avoir réalisé une implémentation différente.
  - Une solution (Julien) propose de créer une classe `MyColor`, et de gérer le rendu avec cette classe. Toute la logique autour des couleurs est retravaillée, afin d'avoir une couleur personnalisée (ici `MyWhiteColor` et `MyBlackColor`)
  - Une autre implémentation suggère de créer 2 sous classes de la classe Square : `MyWhiteSquare` et `MyBlackSquare`. Cette solution permet d'éliminer une condition (celle de la couleur de la case). Elle laisse cependant une condition : celle de la couleur de la pièce.
  - Enfin, une dernière solution proposée, est équivalente à la précédente. Il y a juste, pour chaque classes de pièces, 2 sous classes (ex : `MyWhiteRook` et `MyBlackRook`). C'est la solution que j'ai proposée.

### Et ensuite ?

- Je souhaite faire encore quelques modifications sur mon kata, c'est encore améliorable.
- Je voudrais également commencer à réfléchir sur un nouveau kata. Je doute que celui-ci soit terminé pour la fin du projet, mais c'est un bon défi. Le kata est le suivant : `Game Replay`. Personne dans notre groupe n'a encore choisi ce kata, et c'est pourtant une fonctionnalité essentielle dans un jeu d'échecs.
