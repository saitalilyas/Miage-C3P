# Week 1 report

## Léo Defossez

### Learn about collections in Pharo and their iterators

> #### What is a collection and what is it used for?
> Une collection peut être utilisée pour stocker un nombre d'éléments non connu à l'avance.  
> De plus, les collections offrent souvent un moyen d'itérer sur chacun des éléments, ce qui permet d'écrire du code compact et réutilisable.
> 
> #### What kind of collections does Pharo standard library provide?
> ![image](img/Leo/w1/collections-1.png)
>
> #### How do you iterate collections and what are differences between them?
> ![image](img/Leo/w1/collections-2.png)
> ![image](img/Leo/w1/collections-3.png)
> D'autres itérateurs peuvent existés, il suffit de parcourir les méthodes de la classe Collection dans Pharo.
> 
> #### How did you find this information?
> Chacune des captures d'écran ici sont récupérées du [pdf présent dans le Mooc](https://rmod-pharo-mooc.lille.inria.fr/MOOC/PharoMOOC/Week3/C019-W3S09-Iterators.pdf), abordant les itérateurs.

### Learn about conditionals in Pharo

> #### How do you write conditionals in Pharo?
> On utilise les messages ifTrue:ifFalse:, ou ifTrue: ou ifFalse: séparément.  
> **Un exemple de syntaxe:**
>```Smalltalk
>    true ifTrue: [doSomething] ifFalse: [doSomething]
>```
> #### What is different from other programming languages?
> À la différence d'autres langages, ici les conditionnels sont des messages envoyés aux booléens, comme tout autres messages envoyés à des objets.
> De plus, on utilise des blocs en arguments.
> #### Can you think about the benefits and drawbacks of the approach? 
> Je ne vois pas de problème dans cette approche, cependant, certains bénéfices sont présents :
> 1. L'utilisation de conditionnels étant sous le même format que tout autres appels de méthodes, la syntaxe ne diffère pas du reste du code.
> 2. L'utilisation de bloc permet à ces méthodes d'être *Lazy*
> 
> #### How did you find this information?
> Des [slides à ce propos](https://rmod-pharo-mooc.lille.inria.fr/MOOC/PharoMOOC/Week2/C019-W2S08-BooleansAndCondition.pdf) sont présents dans le MOOC.

### Learn how to create classes and methods

> #### What program did you write?
> J'ai écrit un "mini-jeu" sur [ce dépôt git](https://github.com/LeoDefossez/NTME_pharo/tree/master)
> Très peu de choses sont présentes, mais cela contient des classes, méthodes et 3 tests
> #### What problems did you find? 
> Connaissant déjà pharo, je n'ai pas eu de problèmes particuliers


### Learn about the basic Pharo coding style

> ####  What rules are common to follow?
> 1. indenter le code des méthodes
> 2. ne pas nommer les setter de cette façon :   
> `setAttribute:`  
> mais plûtot de cette façon :  
> `attribute:`  
> 3. autres règles [ici](https://books.pharo.org/booklet-WithStyle/pdf/WithStyle.pdf)
> 
> #### Are there tools that show you violations to such rules?
> Oui, il y en a plusieurs, ceux que je rencontre les plus souvent sont :  
> 1. L'onglet se trouvant sous l'éditeur de méthodes
> 2. L'onglet apparaissant avant de commit
> D'autres sont surement présents, mais je ceux-ci sont ceux que je rencontre les plus souvent. 
