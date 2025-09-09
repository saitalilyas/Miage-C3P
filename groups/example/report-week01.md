
# Olivia

## Collection

Une collection est une structure de données qui peut contenir des objets. Il peut s'agir d'une liste (Array), d'une dictionnaire (Dictionary),  d'un ensemble (Set) ou d'une collection ordonnée (OrderedCollection) dont le premier élément est à l'indice 1. Il existe plusieurs méthodes afin d'effectuer les opérations de base (créer, ajouter, tester, accéder, ...)

Pour itérer sur une collection, on peut utiliser **collect:[unBloc]** 

```
#(11 38 3 -2 10) collect: [ :each | each odd ].
```
Dans cet exemple, on a :each qui est un argument du bloc et qui va prendre en valeur la valeur courante de la collection.  Pour cette valeur on va vérifier si la valeur est impaire. Le résultat sera donc :
```
(true, false, true, false, false)
```

> _Lecture des diapos : An Overview of Essential Collections, Introduction to Blocks_

## Conditionnel
Pour tester des valeurs, on peut utiliser le conditionnel qui se formule :
```
(condition)
    ifTrue : [...] 
    ifFalse : [...]

ex : 
(12>5)
	ifTrue: [ ^1 ]
	ifFalse: [ ^0 ]

> cela va retourner 1
```
Il est différent des autres langages qui utilisent souvent **if-else, if-then-else, if-else if...**

Avec ce conditionnel, il n'y a que deux alternatives : soit la condition est vraie, soit elle est fausse.

> _Vu avec le tutoriel ProfStef_

## Classes et méthodes 
Pour créer une classe, il faut d'abord créer un package. Dans une classe, on peut déclarer une méthode **initialize** qui sert de "constructeur" avec un super et possiblement une initialisation des variables :
```
initialize
    super.
    count := 0
```
On peut également créer des accesseurs. Pour retourner la valeur d'une variable, on utilise le "^"
```
count 
	^count
```
Pour modifier la valeur d'une variable
```
count: anInteger
	count := anInteger
```

> _Vu avec l'exercice Compteur_

NB : je n'ai pas réussi à mettre sur Github l'exercice.

## Pharo coding style 
- Utiliser le camelCase pour les noms de variable et méthode, seuls les noms de classe commencent par une majuscule
- Utiliser des noms explicites : par exemple une méthode de test commence par "test-"
- Il n'y a pas forcément de caractère ";" à la fin de chaque ligne, le code en Pharo est linéraire. Le caractère ";" est utilisé pour les cascades.

## Extras

Les cascades sont définies par le caractère ';'. Celui-ci est utilisé pour enchaîner les commandes afin d'éviter la répétition de codes. Par exemple, au lieu d'écrire : 
```
ProfStef next.
ProfStef next.
```
On va écrire : 
```
ProfStef
    next ;
    next ;
``` 
Ainsi la classe ProfStef n'est pas répétée.

## Ce que je n'ai pas compris

Les loops (avec to-do)

## Modules vus

Module 0 : M0-1 (video + PDF), M0-2 (video + PDF), M0-3 (PDF), M0-4 (video), M0-7 (video), M0-8 (video), M0-9 (PDF), M0-12 (PDF)

Module 1 : 
