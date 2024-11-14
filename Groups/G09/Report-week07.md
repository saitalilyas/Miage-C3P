# Rapport Hebdomadaire Semaine 7 de Salas Merzouk

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