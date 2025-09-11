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
> Il n'est pas du tout interactif, très peu de choses sont présentes, mais cela contient des classes, méthodes et 3 tests
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

### Extras

> #### Can you learn about cascades and block closures?
> **Cascades**
> Exemple :
> ```Smalltalk
>    Transcript open;
>    clear;
>    nextPutAll: 'wow a tab just opened';
>    yourself.
>```
> Le charactère ';' permet d'envoyer des messages en cascades à un objet.  
> Dans le cas ici présents comme on écrit le premier ';' après open, la cascade sera réalisée sur l'objet Transcript. 
> Ce qui signifie que Transcript va effectuer les méthodes open, clear, nextPutAll: et yourself
> yourself permet de renvoyer l'objet initial sur lequel la cascade s'est réalisée, si nous avons besoin de le récupérer
> 
> **Block closure**
> Les blocks peuvent être apparentés à méthodes anonymes ou lambda methods. Ils ne s'exécutent que si nécessaire, ce qui permet de controller une execution. 

# Week 1 report

## Gautier Louvier

### Learn about collections in Pharo and their iterators

> #### What is a collection and what is it used for?
> 
> Une collection dans pharo: est un objet contenant d'autre objet on obtient donc une forme de stockage qui peut avoir certaines spécificité selon les cas d'usage. 
> 
> On peut aussi réaliser des boucles sur celle ci pour executer un bout de code sur chaque élément. 
> 
> 
> 
> #### What kind of collections does Pharo standard library provide?
> 
> On peut retrouver une multitude de collection j'ai trouvés dans les vidéos / slides cette images qui je pense sont les standard library.
> ![(collectionHierarchy)](./img/Gautier/TypeOfCollections.png)
> 
> #### How do you iterate collections and what are differences between them?
> 
> On peut par exemple itéré en selection de maniere spécfique ce que l'ont veut garder avec "select:"  et avec une query specifique.
> 
> ![(image selectIterator)](./img/Gautier/selectIterator.png)
> 
> 
> 
> On peut aussi retrouver l'itérateur "collect:"  qui va récupérer par exemple tout les résultats d'un block pour le ranger dans une collections qui peut être return. 
> 
> ![(iteratorCollect)](./img/Gautier/collectIterator.png)
> 
> #### How did you find this information?
> 
> Sur les screen dans la section du module 1. D'autre itérateur que j'ai trouvé sur les slides : 
> 
> 
> ![basicsIterator](./img/Gautier/BasicsIterators.png)
> 
> 
> ![MoreIterators](./img/Gautier/MoreIterators.png)

### Learn about conditionals in Pharo

> #### How do you write conditionals in Pharo?
> 
>     Les conditions s'écrive comme des messages c'est à dire pour executer True  il faut envoyer le message "ifTrue" avec son argument donc ifTrue:Argument (c'est donc un keyword si j'ai bien compris)
> 
> 
> 
> J'ai pris l'exemple de True et False mais c'est la même chose avec for,while,do ect. . .
> 
> #### What is different from other programming languages?
> 
> On appel directement les messages respectif pour les boolean pour réaliser l'opération dessus. Avec IfFalse et IfTrue 
> 
> #### Can you think about the benefits and drawbacks of the approach?
> 
> Je dirais que ça évite de devoir apprendre une nouvelle syntaxe spécifique au condition, vu que ce sont des objets comme tout le reste et donc on intéragit de la même maniere avec eux. Je sais pas si on peut appeler ça un point négatif mais je dirais que par conséquent si ça ressemble à tout le reste c'est peut etre plus dur à detecter dans un grand code ? Sinon je ne vois pas trop d'inconvénients.
> 
> 
> 
> #### How did you find this information?
> 
> ![imageCondition](./img/Gautier/Conditional.png)
> 
> J'ai déduit ces informations avec ce slide.

### Learn how to create classes and methods

> #### What program did you write?
> 
> J'ai fais le petit programme Counter.
> 
> #### What problems did you find?
> 
> 

### Learn about the basic Pharo coding style

> #### What rules are common to follow?
> 
> On utilise le camelCase pour que ce soit cohérent.
> 
> 
> Une regle qui me paraissait intéressante aussi : 
> 
> 
> 
> #### Are there tools that show you violations to such rules?
> 
> On peut voir ça dans cette partie : 
> 
> ![violationRules](./img/Gautier/violationView.png)
