
# Report Week 6 : Double Dispatch
## Seïf-Eddin
### Exercice 
To practice double dispatch I do the exercice about rock paper scisors mention on week 6

### HomeWork 
This week because I finished already the kata i focus on upgrading it by refactor the code that wasn't good, adding test to check if every thing can work correctly and thinking about adding some feature to make it more close to real chess games when they have to promote pices like chess.com

## Camille BARTHELEMY
### HOMEWORK 

Cette semaine, j'ai regardé des vidéos à propos du double dispatch. J'ai donc pu expérimenter celui-ci directement dans mon kata. J'ai auparavant réalisé les tests (avec les tests de mutations pour montrer que mes tests sont bien ok), il fallait donc que je commence le refactoring en veillant à la non-regression.

J'ai effectué un premier refactoring dans lequel j'ai crée deux classes qui héritent de MyChessSquare : MyChessBlackSquare et MyChessWhiteSquare. Elles disposent donc actuellement des render pour chaque type de pièce.

J'ai également utilisé le Hook and Template pour la méthode contents: (dans la classe MyChessSquare) qui utilise une méthode définie dans MyChessBlackSquare et MyChessWhiteSquare.

Pour finir j'ai vérifié que aucune régression n'avait était introduite en lançant mes tests. Tout est ok. Je peux donc continuer à réfléchir pour améliorer le code.

## Maggy

### 1. Exo

J’ai implémenté le jeu de "Pierre, Papier, Ciseaux, Lézard, Spock" en utilisant le double dispatch. Permettant d’enlever plusieurs if, ce qui rend le code plus modulaire et puissant.
Le double dispatch peut être symétrique, comme dans le jeu, mais il peut également être asymétrique selon les besoins de l'application.
En réalisant les exercices Die et DieHandle, j'ai compris que le double dispatch est un moyen efficace de sélectionner la bonne méthode en fonction du receiver et de l'argument, ce qui renforce la flexibilité du code.

Les exercices y concernant peuvent être consulté depuis : [lien github](https://github.com/s-mgy/double-dipatch/tree/master/src/exoDoubleDispatch).

---

### 2. Kata Graphical Editor

Et pour mon Kata, j’ai fini l’implémentation de base de l’édition, suppresion, l’ajout de toutes les pièces et le resume game. Mais je dois encore faire les test UI et refactoring.
