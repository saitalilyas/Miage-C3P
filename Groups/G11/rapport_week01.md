## Thomas LIENARD

### Learn about collections in Pharo and their iterators

Les collections sont des structures qui permettent de contenir n’importe quel type d’objet. La bibliothèque standard de Pharo fournit beaucoup de classes de collection telles que les Set, Array ou Dictionary qui héritent toutes de la classe Collection, ce qui permet d’avoir une API commune. Pour itérer dans une collection, on peut utiliser le message ```do: aBlock```. Toutes les collections commencent à l’indice 1.

Pour répondre à ces questions sur les collections, j’ai regardé la vidéo ‘Un survol des principales collections’.

### Learn about conditionals in Pharo

Pour écrire une condition en Pharo, on doit d’abord écrire une expression qui retourne un booléen, suivie de ```ifTrue:[]``` et  ```ifFalse:[]```. Le ‘[]’ contient le bloc à utiliser en fonction du résultat. Contrairement à d’autres langages, Pharo vérifie juste qu’un booléen soit vrai ou faux, ce qui me semble plus efficace et plus rapide.

Pour répondre à ces questions sur les conditions, j’ai regardé la vidéo ‘Booléens et conditions’.

### Learn how to create classes and methods

Pour cette partie, j'ai créé la classe Counter et ses quelques méthodes proposé comme tutoriel lors de cette première semaine. 
Voici le dépot de cette classe : https://github.com/Murddy/Counter/tree/main .

Durant cette parti j'ai eu quelque problème pour trouver comment lié ma classe écrite sur mon pc et le git que j'avais créé pour elle. J'ai donc demandé à un camarade de m'expliquer comment faire.

### Learn about the basic Pharo coding style.

Pharo possède plusieurs règle à suivre tels que mettre une majuscule pour commencer le nom d'une classe et mettre une minuscule pour une méthodes. Il y a aussi toute la synthaxe à connaitre comme savoir que || servent à definir une variable ou ^ qui est le return.

Pharo nous montre automatiquement les parties du code qui enfreignent une règle et nous montre la règle enfreinte.

Pour donner un exemple simple : 
```
Nomdemethod
  "commentaire"
  instruction
```
Dans cette exemple le nom de la méthode n'est pas valide.

### Extras

## Baptiste PARENT

### Learn about collections in Pharo and their iterators
Une collection est une structure de données qui peut contenir des éléments, elles sont utilisées pour stocker des informations et pouvoir appliquer des opérations sur un groupe d'éléments plus efficacement.

On peut retrouver les collections suivantes :
- OrderedCollection qui a une taille dynamique 
- Array qui a une taille fixe
- Set qui ne contient aucun doublon
- Dictionary qui est du type associatif (clé - valeur)

Différent itérateur :
- Do: applique le code d'un block à chaque élément.

    ``` #(1 2 3) do: [:each | Transcript show: each; cr]. ```
- collect: fait la même chose que do en retournant en plus une nouvelle collection avec le résultat.

    ``` #(1 2 3) collect: [:each | each * 2]. ```
- select: retourne une nouvelle collection avec uniquement les éléments qui correspondent à la condition du block

    ``` #(1 2 3 4) select: [:each | each even]. ```

J'ai trouvé ces informations sur le MOOC programmation object immersive en pharo.
### Learn about conditionals in Pharo

On a comme conditionnel en pharo:

ifTrue:, ifFalse:, ifTrue:ifFalse:, isEmpty:, isNotEmpty:

Les conditionnels sont des messages envoyés à des objects booléens, true et false sont des instances unique des classes True et False.

### Learn how to create classes and methods

Il faut d'abord créer un package à l'intérieur duquel on peut créer des classes. On peut alors dans chaque classe créer les méthodes voulues.

Je me suis entraîné avec le projet proposé en cours pour créer un compteur, vous pouvez retrouver le code sur l'adresse suivante : https://github.com/BlueBat15/Mycounter

### Learn about the basic Pharo coding style.

Parmis les bonnes pratique de programmation en général on retrouve le nommage explicite des variables et méthodes, suivre le principe de responsabilité unique pour garder des méthodes courtes et un code organisé (et tous les principes SOLID au final).
Il faut aussi bien sûr commenter son code, passer à la ligne et utiliser l'indentation pour la clarté du code.

Je ne sais pas à propos d'outils supplémentaire mais en codant dans l'IDE pharo j'ai pu voir qu'il y avait des warning sur les bonnes pratique à suivre notamment commencer un nom de méthode de test par "test" et finir un nom de classe de test par "tests". 

### Extras

Les cascades permettent d'envoyer plusieurs message à un même objet sans avoir à le répéter. J'ai pu l'utiliser dans les tests du projet Mycounter.

``` c count:2; decrement; decrement. ```

Qui est équivalent à :
``` 
    c count:2.
    c decrement.
    c decrement 
```

Les blocks contiennent du code qui ne s'exécute pas immédiatement et peut être passé en paramètre pour le stocker. On peut l'évaluer en utilisant le message value:

``` [:x | x + 2] value: 5 "retourne 7```


## Alyocha Yahi

# Homework/Report

For next week's lecture, you need to do the following tasks and prepare a short report on how you approached them. Each of the following tasks will guide your work with questions. You must answer those questions in the report.

### Learn about collections in Pharo and their iterators

## What is a collection and what is it used for?


La programmation avec des fonctions d'ordre supérieur permet de manipuler des collections de manière abstraite, en appliquant des fonctions à tous les éléments d'une collection sans avoir à traiter chaque élément individuellement. Pharo, comme Smalltalk, adopte cette approche où des fonctions comme `select:` permettent de filtrer une collection selon des critères spécifiés, offrant ainsi une syntaxe élégante et simple.

Par exemple, pour sélectionner les étudiants ayant une moyenne inférieure à un seuil, on écrit simplement :

```smalltalk
students select: [ :each | each gpa < threshold ]
```

Cela retourne une nouvelle collection avec les étudiants correspondant au critère. Ce type de code est plus simple et plus lisible que l'utilisation de boucles impératives.

Pharo définit un ensemble de protocoles standard utilisés par toutes les collections pour tester l'appartenance (par exemple, `includes:`), itérer sur les éléments (comme `do:`, `select:`, `collect:`), ou les convertir entre différents types. Ces méthodes permettent de manipuler les collections de manière uniforme, quelle que soit leur structure sous-jacente (tableau, liste chaînée, etc.), rendant le code plus flexible et facile à maintenir.


## What kind of collections does Pharo standard library provide?

1. **Tableaux (Arrays)** : Les tableaux stockent leurs éléments dans des variables d'instance indexables au sein de l'objet collection. Ils ont une taille fixe, mais cette taille est allouée d'un seul coup en mémoire. L'accès aux éléments se fait via des indices, mais on ne peut pas ajouter ni retirer d'éléments une fois le tableau créé.

2. **Collections ordonnées (OrderedCollections) et triées (SortedCollections)** : Ces collections stockent les éléments dans un tableau référencé par une variable d'instance. Contrairement aux tableaux, ces collections peuvent grandir, et leur tableau interne peut être remplacé par un plus grand si nécessaire. Dans une `OrderedCollection`, les éléments sont ajoutés dans l'ordre d'insertion, alors que dans une `SortedCollection`, les éléments sont maintenus dans un ordre trié.

3. **Ensembles (Sets) et Dictionnaires (Dictionaries)** : Ces collections utilisent un tableau secondaire en tant que table de hachage. Dans un ensemble, chaque élément est unique et sans ordre. Un dictionnaire permet d'associer des clés à des valeurs. Les éléments d'un `Bag` (un type particulier de collection) sont utilisés comme des clés dans un dictionnaire, et les valeurs sont le nombre d'occurrences des éléments.

4. **Listes chaînées (LinkedLists)** : Ces collections utilisent une représentation chaînée simple où chaque élément pointe vers l'élément suivant, ce qui permet une manipulation dynamique des éléments, comme l'ajout ou la suppression rapide.

5. **Intervalles (Intervals)** : Un intervalle est une collection représentée par trois entiers : les deux bornes de l'intervalle et le pas (la taille de l'incrément entre chaque élément). Cela permet de définir des gammes de valeurs continues, comme des nombres entre 1 et 100.

6. **Collections faibles (Weak collections)** : Ces collections sont des variantes des tableaux, ensembles et dictionnaires où les éléments sont retenus faiblement, ce qui signifie qu'ils peuvent être collectés par le ramasse-miettes si aucune autre référence n'existe. Cela peut être utile pour éviter les fuites de mémoire dans certains cas d'utilisation.

### How do you iterate collections and what are differences between them?

## 1. **Itération de base avec `do:`**
La méthode `do:` est l'itérateur de base pour parcourir une collection. Elle applique un bloc de code à chaque élément de la collection. Par exemple, pour afficher tous les éléments d'un tableau de chaînes dans la fenêtre de transcript :

```smalltalk
#('bob' 'joe' 'toto') do: [:each | Transcript show: each; cr].
```

Cela itère sur chaque élément (ici les chaînes `'bob'`, `'joe'`, `'toto'`) et les affiche dans le `Transcript`.

## 2. **Itération avec l'index : `doWithIndex:`**
Si vous avez besoin de l'indice de chaque élément dans la collection, vous pouvez utiliser `doWithIndex:`. Cela permet de recevoir à la fois l'élément et son indice dans le bloc.

```smalltalk
#('bob' 'joe' 'toto') doWithIndex: [:each :i | (each = 'joe') ifTrue: [ ^i ]].
```

Ici, la méthode renvoie l'indice où `'joe'` apparaît dans la collection, soit `2`.

## 3. **Itération à l'envers : `reverseDo:`**
Pour parcourir une collection dans l'ordre inverse, vous pouvez utiliser `reverseDo:`. Cela permet de parcourir les éléments en partant de la fin de la collection.

```smalltalk
#('bob' 'joe' 'toto') reverseDo: [:each | Transcript show: each; cr].
```

## 4. **Itération avec une séparation : `do:separatedBy:`**
Cette méthode permet d'exécuter un bloc entre deux éléments, en ajoutant un séparateur à chaque itération. Par exemple, pour concaténer des chaînes avec un séparateur :

```smalltalk
| res |
res := ''.
#('bob' 'joe' 'toto') do: [:e | res := res, e] separatedBy: [:e | res := res, '.'].
res
```

Cela renverra la chaîne `'bob.joe.toto'`.

## 5. **Dictionnaires : itération sur les clés et les valeurs**
Les dictionnaires offrent des messages spécifiques pour itérer sur leurs clés, valeurs ou associations (paire clé-valeur). Voici comment itérer sur un dictionnaire :

```smalltalk
colors := Dictionary newFrom: { #yellow -> Color yellow. #blue -> Color blue. #red -> Color red }.
colors keysDo: [:key | Transcript show: key; cr].   "Affiche les clés"
colors valuesDo: [:value | Transcript show: value; cr]. "Affiche les valeurs"
colors associationsDo: [:association | Transcript show: association; cr]. "Affiche les associations"
```

## 6. **Collecter des résultats avec `collect:`**
Si vous souhaitez appliquer une fonction à chaque élément d'une collection et obtenir une nouvelle collection contenant les résultats, vous pouvez utiliser `collect:`. Voici un exemple pour doubler les éléments d'une collection :

```smalltalk
#(1 2 3 4 5 6) collect: [:e | 2 * e]
```

Cela renverra une nouvelle collection `#(2 4 6 8 10 12)`.

## 7. **Sélectionner ou rejeter des éléments : `select:` et `reject:`**
Utilisez `select:` pour obtenir les éléments qui satisfont une condition, ou `reject:` pour ceux qui ne la satisfont pas. Par exemple :

```smalltalk
(2 to: 20) select: [:each | each isPrime]
```

Cela renverra tous les nombres premiers de 2 à 20. En revanche, pour rejeter les nombres premiers :

```smalltalk
(2 to: 20) reject: [:each | each isPrime]
```

## 8. **Détecter un élément : `detect:`**
Le message `detect:` permet de trouver le premier élément qui satisfait une condition :

```smalltalk
'through' detect: [:each | each isVowel]
```

Cela renverra la première voyelle trouvée, ici ` $o`.

## 9. **Accumulateur avec `inject:into:`**
Si vous souhaitez accumuler des résultats avec une opération binaire (comme la somme ou le produit), vous pouvez utiliser `inject:into:`. Par exemple, pour calculer la somme des premiers 100 entiers :

```smalltalk
(1 to: 100) inject: 0 into: [:sum :each | sum + each]
```

Cela renverra `5050`.


## How did you find this information?


Source : "Pharo 9 by Example", Chapitre 1 :"Collection"

Do not hesitate to add in the report code examples that you tried.

## Learn about conditionals in Pharo

### Comment écrivez-vous des conditionnelles en Pharo ?

En Pharo, les conditionnelles sont écrites comme des messages envoyés à des objets booléens ou des blocs. Les constructions traditionnelles comme `if`, `else` et `while` que l'on trouve dans d'autres langages de programmation ne sont pas utilisées directement. À la place, Pharo utilise la syntaxe d'envoi de messages pour les conditionnelles. Par exemple, `ifTrue:` et `ifFalse:` sont des messages envoyés à des valeurs booléennes (comme `true` ou `false`).

Voici quelques exemples :
- `ifTrue:` : Un message envoyé à un booléen qui exécute le bloc si le booléen est `true`.
  ```smalltalk
  Weather isRaining ifTrue: [ self takeMyUmbrella ].
  ```
- `ifFalse:` : Un message envoyé à un booléen qui exécute le bloc si le booléen est `false`.
  ```smalltalk
  Weather isRaining ifFalse: [ self takeMySunglasses ].
  ```
- Vous pouvez combiner ces messages pour créer des conditionnelles plus complexes :
  ```smalltalk
  fullName isEmptyOrNil
    ifTrue: [ 'FirstnameLastname' translated ]
    ifFalse: [ fullName ].
  ```

### Qu'est-ce qui est différent par rapport à d'autres langages de programmation ?

La principale différence par rapport à de nombreux autres langages de programmation est qu'en Pharo, **les conditionnelles ne sont pas des structures de contrôle** classiques. Au lieu de cela, les conditionnelles sont traitées comme des **messages** envoyés à des **objets booléens** ou des **blocs**.

Dans la plupart des langages, une expression conditionnelle (comme `if` ou `else`) est une construction syntaxique intégrée. En Pharo, cependant, `ifTrue:`, `ifFalse:`, et d'autres conditionnelles similaires ne sont que des messages envoyés à des valeurs booléennes. Cette approche est cohérente avec la philosophie de Pharo, où tout est un objet, y compris les booléens et les conditionnelles.

Une autre différence notable est l'utilisation de l'**évaluation paresseuse** pour les opérateurs logiques comme `and:` et `or:`. Dans les langages traditionnels, les opérateurs logiques évaluent généralement les deux opérandes, mais en Pharo, les opérateurs `and:` et `or:` sont paresseux. Cela signifie que le deuxième argument n'est évalué que si nécessaire :
```smalltalk
false and: [ 1 error: 'crazy' ] "Pas d'erreur car le deuxième bloc n'est pas exécuté"
```

### Quels sont les avantages et les inconvénients de cette approche ?

**Avantages :**
1. **Cohérence** : Puisque les conditionnelles sont des messages, tout est traité comme un objet en Pharo. Cette approche uniforme permet un style de programmation plus cohérent et orienté objet.
2. **Flexibilité** : Vous pouvez facilement étendre ou modifier le comportement des conditionnelles en créant des messages personnalisés, ce qui permet d'adapter la logique conditionnelle à des besoins spécifiques.
3. **Évaluation paresseuse** : L'évaluation paresseuse des opérateurs logiques (`and:` et `or:`) est une fonctionnalité puissante qui peut améliorer les performances dans certaines situations. Elle empêche l'exécution de calculs inutiles en n'évaluant le deuxième argument que si le premier ne détermine pas déjà le résultat.

**Inconvénients :**
1. **Moins intuitif pour les débutants** : Pour les développeurs venant d'autres langages, cette approche peut sembler moins intuitive. L'idée d'envoyer des messages à des booléens plutôt que d'utiliser des structures de contrôle traditionnelles comme `if` et `else` peut être déroutante au début.
2. **Moins familier** : L'approche de Pharo pour les conditionnelles et le flux de contrôle peut rendre plus difficile la transition vers ou depuis d'autres langages avec une syntaxe plus conventionnelle, ce qui peut compliquer la collaboration ou le partage de code.
3. **Verbosité** : Bien que le fait que tout soit un message permette une grande flexibilité, cela peut entraîner un code plus verbeux comparé à la syntaxe compacte de `if-else` que l'on trouve dans d'autres langages.

### Comment avez-vous trouvé ces informations ?

Source : 
Learning Object-Oriented
Programming and Design with TDD
Booleans and Conditions
Stéphane Ducasse

Do not hesitate to add in the report code examples that you tried.

## Learn how to create classes and methods

How do you write a small program with classes and methods in Pharo?
Pharo is indeed, very IDE oriented and you have to get used to the tooling.
How did you find this information?

What program did you write?
Un simulateur de compteur qui s'incremente ou decrémente
What problems did you find?
le cours n'était pas en pharo 12.0 et la façon de déclarer les fonctions, par exemple, n'était pas à jour.
Please provide a github repository link.





