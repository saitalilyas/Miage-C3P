### Obede :
#### Learn about Collections in Pharo
-In Pharo, a collection is an object that groups other objects together.
It is used to:
	•	Store multiple elements (numbers, strings, objects, …)
	•	Organize them (ordered, unordered, unique, key-value, …)

Exemple of collection
#(1 2 3) wiht numbers
#('Obede' 'Jean' 'Adil') with strings

For iteration here is the example i tried

	t := #('Obede' 'Jean' 'Adil') do: [ :each | Transcript show: t].

#### Learn about Conditionals
In Pharo, conditionals are not keywords (like if, else in Java or Python), but instead messages sent to Boolean objects (true and false).

Code i tried

	(3 > 2) ifTrue: [Transcript show: 'Yes, 3 > 2'].
	(3 < 2) ifFalse: [Transcript show: 'Yes, 3 is not < 2']
---

### Jean-Alexis :

#### Collections :

  - A collection is a list of objects, it used to groups some objects "in the same variable".
  - Pharo standard library provide iterative collections (i'm not sure about this name)
  - We can iterate with commands do: if we want to show the data, select: if we want to filter it or even collect: for do operations on it.

  Here are some examples that I tried :

  ```
  #(45 56 76 34) select: [ :each | each odd ].
  
  #(45 56 76 34) collect: [ :each | each * 5 ].
```

#### Conditionals 

Conditionals in Pharo can be used like this : 

```
(condition)
  ifTrue: [instruction if it's true]
  ifFalse: [instruction if it's false].
```

The difference with other programming languages is the "limit" of conditionals, here we have one condition and only two cases : it's true or false. In the other languages we can add an 'else if' and make an other condition.
I think it's benefit in Pharo because you won't have a big and too long conditions that will be difficult to undestand. Like this it will be verry simple and understandable to everyone.

  Here are some examples that I tried :

```
(5 < 7)
	ifTrue: [ 'Il y a une erreur dans la matrice !' ]
	ifFalse: [ 'RAS Aucun problème détécté !' ] inspect.
"L'inspecteur doit surligner la deuxième phrase."
```

#### Classes and methods

*I'll complete this section later.*

#### Basic Pharo coding style

There are some rules to follow, some of them are same as the others languages like the spaces "to give breath to code". Others are only in Pharo as far as I know like the comments placed under the method definition. 
I will not repete all theses but we can found the main and most importants rules on the [this graph](https://github.com/SquareBracketAssociates/Booklet-PharoWithStyle/blob/master/Chapters/PWS-Guidelines-1.pdf).

#### Note

All these informations come from my web research, specially [the documentation](https://github.com/pharo-open-documentation/pharo-wiki) and the courses of this current repository (and maybe sometime a little bit from my mind and my memory).

---

### Adil :
