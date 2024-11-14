# AIT YAHIA Maya 

Cette semaine en cours, nous avons étudié les concepts de Template Method et de Hooks en programmation orientée objet. Ces modèles permettent de structurer un algorithme général tout en laissant aux sous-classes la possibilité de redéfinir certaines étapes spécifiques.

## Template Method
La Template Method est une méthode dans la superclasse qui définit les étapes générales d'un algorithme. Elle fixe une structure commune tout en déléguant certaines étapes aux sous-classes.

## Hook
Un Hook est une méthode dans la superclasse, souvent vide ou avec un comportement par défaut. Il peut être redéfini dans les sous-classes pour adapter l’algorithme à des besoins spécifiques.

## Exemple dans le projet d’échecs
Dans le projet d’échecs, on retrouve ces concepts dans la méthode targetSquare. Elle agit comme une Template Method qui définit la logique générale pour cibler une case. La méthode targetSquareLegal est utilisée comme un Hook et redéfinie dans chaque sous-classe pour adapter le comportement de chaque type de pièce.
