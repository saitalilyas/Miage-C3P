# Rapport FINAL - semaine n°10 - Groupe 10

Lien du projet : [chess-group-10 - GitHub](https://github.com/AymericJak/chess-group-10/tree/main)

## Elsa Logier

### Le projet Chess

Depuis mon dernier rapport, j'ai réussi à comprendre la logique du "en passant" et après quelques jours à avoir travaillé dessus j'ai réussi à implémenter la logique de base du mouvement (si un pion a fait son premier déplacement de deux cases et qu'il est à côté de mon pion alors je peux aller en diagonal et passer derrière lui). Il me reste à prendre le pion de la case de gauche si je fais le mouvement.


### Conclusion du cours de Pharo 

Ce cours à été très instructif car il m'a permis de mieux comprendre la notion de orienté objet. Il a aussi changé ma vision des langages et m'a permis de voir la puissance du langage pharo (surtout quand je suis retournée sur d'autres langages après le module)

J'ai trouvé le Mooc très instructif, clair et avec des exemples qui m'ont permis de comprendre et je suis heureuse d'avoir pu poser mes questions en cours lorsque je n'étais pas sure d'avoir compris une notion parfaitement.

Le projet Chess m'a permis d'appliquer mes apprentissages et de nous réunir avec certaines personnes de la classe afin de réfléchir ensemble aux solution possibles pour différents problèmes complexe que nous avons rencontrés. Cela nous a permis d'apprendre majoritairement en autonomie tous ensemble et j'ai trouvé ca très intéressant.

## Aymeric Jakobowski

### Le projet

Sur cette fin de projet, j'ai finalement fait diverses améliorations au lieu de commencer un nouveau kata. Parmi ces améliorations, on peut retrouver l'amélioration des tests unitaires, de la réécriture de bouts de code ou encore de la correction de bugs.

Par exemple, dans certaines fonctions, nous avions ce morceau de code `(square down left notNil and: square down left hasPiece)`. Dans l'absolu, rien de faux, le programme fonctionne, mais le comportement du n'est pas celui que l'on souhaite lors de l'exécution. Dans ce cas, nous souhaitons que si la première partie de la condition est fausse, on ne fasse pas la suite. Mais sous cette forme la partie gauche et droite du 'end' s'exécutent.
Il faut en réalité mettre la partie droite du 'and' sous forme de bloc comme suit `(square down left notNil and: [ (square down left) hasPiece ])`. Ainsi, sous cette forme, il peut y avoir court-circuit.

J'ai corrigé des problèmes liés à la capture des pièces qui ne fonctionnait plus, un bug qui empêchait le fonctionnement du bouton 'play!', etc.

### Conclusion de ce cours

Certes, je n’ai pas brillé aux devoirs sur table, parce que je trouvais ça trop compliqué pour moi. Mais ce cours m’a quand même appris énormément de choses. Il a notamment changé ma façon d'appréhender la programmation orientée objet.

Ça peut sembler un peu bête, mais je ne m’étais jamais demandé comment étaient implémentés les opérateurs logiques or et and. Avant, j’aurais bêtement pensé que l'implémenttaion est sous forme de condition condition, alors que pas du tout ! Ce cours m’a donc permis de réfléchir à des choses auxquelles on ne pense pas d’habitude et de sortir un peu de ma zone de confort

Bien que je ne sois pas un pro, j’ai aujourd’hui plus de clés en main, à la fois sur la méthode d’apprentissage et de pratique, et sur certains concepts techniques comme le double dispatch, le composite, la stratégie…

Travailler sur le projet d’échecs (en espérant que ce ne soit pas une métaphore de mon résultat final dans la matière) m’a beaucoup plu. C'est un jeu qui me parle. Cependant, un petit regret : avoir passé trop de temps à réaliser mon premier kata, j'avais particulièrement envie de débuter le second sur le replay d'une partie.
