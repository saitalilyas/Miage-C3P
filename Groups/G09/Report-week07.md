# Rapport Hebdomadaire Semaine 7

# - Salas Merzouk

Cette semaine, j'ai poursuivi mon travail sur mon kata (remove NIL checks). Mon objectif était de traiter le défi suivant : "Something similar happens when a pieces wants to move outside of the board, can you find it and fix it?"

J'ai passé du temps à étudier le code existant pour comprendre comment les mouvements des pièces sont gérés lorsqu'elles atteignent les limites du plateau. Cette analyse m'a permis d'identifier les points où le polymorphisme pourrait être utilisé pour remplacer les vérifications actuelles, de manière similaire à ce qui a été fait pour les autres vérifications de nil dans le projet.

## Préparation du cours de cette semaine

J'ai également préparé le prochain cours en étudiant les slides sur le Composite Pattern. Cette lecture m'a permis de comprendre comment ce pattern de conception peut être utilisé pour traiter uniformément des objets individuels et des collections d'objets, ce qui pourrait potentiellement être utile dans le contexte de mon kata.

#  - Salim TITOUCHE 

Après avoir résolu la majorité des problèmes liés aux mouvements des pions, cette semaine, j'ai réfléchi à une manière de simplifier les grands blocs de conditions `if else`. 

## Discussions et idées
J'ai discuté avec mes camarades pour obtenir des idées. L'objectif était de structurer le code de manière plus modulaire et lisible.

## Implémentation
J'ai commencé par créer deux nouvelles classes :
- `MyWhitePawn`
- `MyBlackPawn`

Ces classes héritent de `MyPawn`. Ensuite, j'ai redéfini dans chaque classe la méthode `targetSquaresLegal` pour gérer les mouvements spécifiques à chaque type de pion.

## Dépôt GitHub
J'ai poussé toutes les modifications sur mon dépôt GitHub.

## Chapitre 11
J'ai également commencé à travailler sur le chapitre 11. Les premières étapes  et je prévois d'avancer davantage cette semaine.

# - André Filho

Pour cette semaine, j'ai commencer à implementer la solution finale de mon kata, en utilisant le model du visitor pour faire la fonction de regarder les pièces qui menacent le roi et lui donner une meilleur notion de comment faire les mouvements sans se metre dans une position menacée

Du coup, l'idee c'est de vérifier toutes les pièces qui sont de la couleur opposée, prendre ses mouvements autorisées et les enlever de la liste de mouvements permis par le roi.

## Law of Demeter

De la côté des études pour le prochain cours, j'ai memorisé la loi de demeter et ses applications et comment elle peut nous aider à avoir une meilleure organization des envois de message dans nos codes.

## Delegation vs Inheritance

Inheritance helps us keep some track of static methods, although it could also lead to more static designs, leading it to be hard to change dynamically. Whilst using delegation and double-dispatch techniques, you can modularize every functionality a bit better for what suits their needs, although it also means that the delegated class needs to have access to the data from the delegator.

In the end, there is not golden-rule or perfect approach, but both these techniques are useful for solving different kinds of problems.