### Obede :


### Jean-Alexis :

#### Collections :

  - A collection is a list of objects, it used to groups some objects "in the same variable".
  - Pharo standard library provide iterative collections (i'm not sure about this name)
  - We can iterate with commands do: if we want to show the data, select: if we want to filter it or even collect: for do operations on it.

  Here are some examples that I tried :

  #(45 56 76 34) select: [ :each | each odd ].
  
  #(45 56 76 34) collect: [ :each | each * 5 ].

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



### Adil :
