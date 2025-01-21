## Thomas LIENARD

### Practice message dispatch

Grâce aux vidéo du mooc, j'ai pu comprendre que le dispatch permet d'éviter l'utilisation de condition qui peuvent être couteuse. Mais aussi qu'un message est un choix dynamique qui depend des classes chargé par exemple si ma classe ```Myclass``` hérite de la classe ```SuperClass``` qui possède la method ```doSomething:``` alors le message ```Myclass doSomething:``` utilisera la method de ```SuperClass```.

J'ai aussi trouvé que le dispatch dynamique ressemble au polymorphisme dans les autres languages tels que java, il permet une forte modularité du code mais aussi d'avoir des classes plus simple. 

Les classes joue le role de choix, donc avoir plusieurs classes ou une seul à un fort impact comme pour l'exemple des booléens avec l'implementation de not vu dans les videos.


* Pour tester le dispatch en Pharo j'ai écrit le code suivant :

```
Object << #Vehicle
  slots: {};
  package: 'Exemple'  

  wheel
    ^ '4' .

  Vehicle << #Car
    slots: {};
    package: 'Exemple'.

  Vehicle  << #Motorcycle
    slots: {};
    package: 'Exemple'.

    wheel 
      ^ '2'.

  | vehicle1 vehicle2 vehicle3|
	vehicle1 := Vehicle new.
	vehicle2 := Car new.
	vehicle3 := Motorcycle new.

    vehicle1 wheel.
    vehicle2 wheel.
    vehicle3 wheel.
```

Je m'attend donc à avoir respectivement '4', '4', '2'. 

Après avoir testé ce code, j'obtient bien ce resultat.

## Baptiste PARENT

### Practice message dispatch

D'après ce que j'ai compris la dispatch c'est le mécanisme qui permet de choisir la méthode exécutée en fonction du message et du receveur. 

En considérant cet exemple : 
```
Object subclass: ParentClass [
    ParentClass >> myMethod [
        ^ 'Méthode Parent'
    ]
]

ParentClass subclass: ChildClass [
    ChildClass >> myMethod [
        ^ 'Méthode Enfant'
    ]
]
```
```
| obj |
obj := ChildClass new.
obj myMethod
```

Dans cet exemple, myMethod est redéfini dans ChildClass. En appelant la méthode myMethod depuis une instance de ChildClass la méthode exécutée sera celle de ChildClass

J'ai appris ce concept en regardant le MOOC.

## Alyocha Yahi

## Amélioration et Explication du Dispatching

Pour approfondir mes connaissances sur le dispatching, j'ai suivi l'exercice "Exercises for Essence of Dispatch" et réalisé plusieurs exercices pratiques. L'objectif était de mettre en œuvre des messages comme `not`, `and`, et `ifTrue:ifFalse` afin d'explorer le dispatching d'un message en fonction du type d'objet récepteur.

## Exemple d'implémentation de `and`

D'abord, j'ai implémenté la méthode `and` pour les classes `True` et `False` :

- Pour la classe `True`, la méthode `and` renvoie l'autre valeur, puisque si l'objet est `True`, c'est l'autre opérande qui détermine le résultat :
  
  ```
  myAnd: aBoolean
      ^ aBoolean
  ```

- Pour la classe `False`, la méthode `and` renvoie immédiatement `False`, puisque si l'objet est `False`, le résultat est toujours `False`, indépendamment de l'autre valeur :

  ```
  myAnd: aBoolean
      ^ False
  ```

Ces implémentations m'ont permis de constater l'importance de la distinction entre `True` et `False`. Chaque classe possède une logique différente qui permet de gérer les opérateurs de manière appropriée. Cela montre également que le dispatching de message est basé sur le type d'objet récepteur.

## Types de Dispatching

Il existe différents types de dispatching :

- **Dispatching unaire** : Exemple avec la méthode `not` sur un objet `True` ou `False`.
  
  ```
  true not.  "Retourne False"
  false not. "Retourne True"
  ```

- **Dispatching binaire** : Exemple avec l'opérateur `and` entre deux objets `True` et `False`.

  ```
  true and: false. "Retourne False"
  false and: true. "Retourne False"
  ```

## Exemple avec l'héritage : `Animal` et `Bird`

Ensuite, j'ai créé deux classes, `Animal` et `Bird`, chacune avec une méthode `speak` :

- La classe `Animal` a une méthode `speak` qui affiche "L'animal fait du bruit".
- La classe `Bird` a une méthode `speak` qui affiche "L'oiseau chante".

Ces deux classes fonctionnaient correctement lorsqu'elles étaient testées séparément dans le Playground.

Ensuite, j'ai créé une classe parente `Animal` pour les classes `Bird` et `Fish`. La méthode `speak` dans `Animal` est définie comme suit :

```
speak
    self subclassResponsibility.
```

Cela oblige chaque sous-classe à implémenter sa propre version de la méthode `speak`.

### Test dans le Playground

L'objectif était de tester le polymorphisme et le dispatching en créant des objets de type `Bird` et `Fish`, et en les manipulant à travers une collection d'objets `Animal`. Voici le code utilisé pour tester :

```
myBird := Bird new.
myFish := Fish new.

animals := { myBird. myFish }.

animals do: [ :each | Transcript show: each speak; cr ].
```

## Résultat attendu et observation

Le résultat attendu était que le message `speak` soit envoyé aux objets `Bird` et `Fish`, et que le script affiche "L'oiseau chante" et "Le poisson fait glouglou". Cependant, lorsque j'ai exécuté le script, je ne voyais pas immédiatement les résultats dans le Transcript. Après vérification, j'ai constaté que je regardais dans le mauvais endroit pour voir les sorties.

L'objectif était de tester que le message correct soit envoyé en fonction du type de chaque objet. Et c'est bien ce qui s'est passé. Selon que l'objet était de type `Bird` ou `Fish`, la méthode appropriée a été appelée, et les résultats étaient corrects.


## Conclusion

Cet exercice m'a permis de mieux comprendre les principes du dispatching et du polymorphisme. J'ai constaté que la gestion des messages dépend de la classe de l'objet récepteur, et que l'héritage joue un rôle crucial dans le dispatching, permettant à chaque sous-classe de fournir sa propre implémentation d'une méthode partagée. Les exemples de `True` et `False`, ainsi que l'usage de la classe parente `Animal`, ont clarifié l'importance de la distinction entre les types d'objets et de leur influence sur le comportement des méthodes appelées.
