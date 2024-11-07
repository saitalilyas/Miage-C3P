# Rapport Pharo - Semaine 6

## André FILHO

For this week, our task was to dive into the Pharo Visitor pattern, focusing on understanding its structure and exploring its potential applications within our project.

I started by examining the concept of the Visitor pattern within the Pharo environment, focusing specifically on its use cases in Pillar. This included analyzing documentation and analysing the MOOC, in which I found some insight comparing the pattern to Double Dispatch.

Attempted Application in Project Context
Eventhough I thoroughly studied the theoretical aspects and reviewed practical examples, I encountered challenges in identifying a relevant use case for applying the Visitor pattern directly within our chess project, especially to my Kata.

Observations and Next Steps

This exploration allowed me to grasp the fundamental mechanics of the Visitor pattern in Pharo, including the advantages it offers in terms of extending functionalities without modifying original classes By contrast, I believe I still miss on some hands-on approach to better understand how it works, which I plan to do whils resolving the exercises next class.

# Week 6 Report - TITOUCHE Salim

## Double Dispatch Study
This week, we explored double dispatch, a fundamental technique in Pharo that leverages the message system to dynamically select appropriate methods based on the types of objects involved. This approach is particularly elegant in Pharo as it integrates naturally with the language's message system.

## Objectives and Review
I deepened my understanding of double dispatch in Pharo, focusing on:

- Specific syntax requirements
- Language naming conventions
- Practical applications for upcoming evaluations

## Exercises Completed
I completed exercises related to:

- Die/DieHandle implementation
- Paper Scissors Stone game

## Chess Game Progress
During this week, I resolved the issues mentioned in Report 5 and implemented the corresponding tests.

## Related Code Links
- [Dice implementation](https://github.com/salim2607/MyCounter/tree/master/src/Dice)
- [Chess game](https://github.com/mrdedede/Chess)


# Rapport Hebdomadaire Semaine 6 de Salas Merzouk

Cette semaine, j'ai travaillé sur un exercice de double dispatch, en mettant en place une version du jeu "pierre, feuille, ciseaux". 
J'ai défini les comportements de chaque choix du jeu (pierre, feuille, ciseaux) pour gérer les résultats sans vérifications conditionnelles, mais en utilisant le dispatch pour appliquer la logique de victoire ou de défaite entre les objets.

Cet exercice m'a permis d'approfondir la logique de double dispatch en implémentant les interactions entre les différentes actions du jeu (pierre contre feuille, pierre contre ciseaux, etc.).

### Préparation du cours de cette semaine 
  
  J'ai également commencé à préparer le cours en lisant les slides intitulés *Visitor: Modular and extensible first class actions*. Cette lecture m'a permis de mieux comprendre l'approche du design pattern Visitor, en particulier l'usage de la modularité et du double dispatch pour séparer les comportements des objets de domaine des opérations appliquées.
  
  J'ai étudié des exemples et les avantages du Visitor dans les systèmes nécessitant des opérations variées sur des structures complexes.

Ce travail sur le double dispatch et le pattern Visitor enrichit ma compréhension des concepts avancés en conception orientée objet et prépare le terrain pour les prochains exercices.

# Week 6 Report - TITOUCHE Salim

## Double Dispatch Study
This week, we explored double dispatch, a fundamental technique in Pharo that leverages the message system to dynamically select appropriate methods based on the types of objects involved. This approach is particularly elegant in Pharo as it integrates naturally with the language's message system.

## Objectives and Review
I deepened my understanding of double dispatch in Pharo, focusing on:

- Specific syntax requirements
- Language naming conventions
- Practical applications for upcoming evaluations

## Exercises Completed
I completed exercises related to:

- Die/DieHandle implementation
- Paper Scissors Stone game

## Chess Game Progress
During this week, I resolved the issues mentioned in Report 5 and implemented the corresponding tests.

## Related Code Links
- [Dice implementation](https://github.com/salim2607/MyCounter/tree/master/src/Dice)
- [Chess game](https://github.com/mrdedede/Chess)
