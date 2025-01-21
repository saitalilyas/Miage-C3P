## DASSI-Helyana

# WEEK 5 :

## HOMEWORK : 
pas d'homework demandé


### Partie cours : 

### HOOK & TEMPLATE 
Ce que j'ai compris: 
Hook = point d'extension (méthode) comme des trous que l'on peut remplir pour ajt/modif un comportement sans changer la structure. 
en revanche : une template methode permet de définir la structure général. 
Les hooks sont implementés grâce aux sous classes 

Voici un exemple simple : 

On a une classe Cuisine qui contient la structure générale du processus pour préparer un repas avec les étapes :
- Préparer les ingrédients
- Cuire
- Servir


Dans la classe Cuisine la methode template preparerRepas def l'ensemble de la préparation du repas 
```
Cuisine >> preparerRepas
  self preparerIngredients
  self cuire
  self servir
```

La classe definit les methodes qui seront redéfinies par les enfants ex : 
```
preparerIngredients 
  self subclassResponsability
```
Ensuite on implemente les hooks preparerIngredients, cuire, selon le type de cuisine (les sous classes : ex CuisineAlgerienne, Cuisine Italienne)




# WEEK 6 : 
## HOMEWORK : 
pas d'homework demandé

## Préparation EXAM 1 :

organisation de révison :
- révision en groupe pour aider à la compréhension de certaines parties du cours à l'aide de call discord 
- j'ai aussi beaucoup pratiqué sur papier (jai prompt chatgpt pour qu'il me donne des exercices 
en augmentant petit à petit la complexite) afin de m'exercer sur la rélisation des tests
- compréhension de la partie mutation testing avec mon camarade

### Difficultée(s) rencontrée(s):
- Impossible de push probleme sur git à cause du token ou autre


### Avancement projet 

- Réalisation du testing de certaines méthodes cibles
- Identification des nils et identification des correspondances ( case vide ou inexistente)



## EL MANSOURI Yacine

# WEEK 5 :

Cette semaine on a decouvert le concept de Template Methode avec les  Hooks. Ce modèle permettent de structurer un algorithme général tout en laissant aux sous-classes la responssabilité de définir certaines spécificités.

- Template Method :  
La Template Method, c'est donc un design patern qui va avoir une méthode dans la superclasse qui définit les étapes générales d'un algorithme. Elle fixe alors la structure commune et delegue certaines étapes aux sous classes qui sont des methodes abstraites.

- Hook :  
Ces methodes abstraites de la super classe sont alors definis par les sous classes, elles sont nommées "hook". Elle permette aux sous classes d'avoir un comportement specifique.

- Pour donner un exemple, on peut en retrouver dans le projet Chess. Dont la méthode targetSquare. Elle agit comme une Template Method qui définit la logique générale pour cibler une case. Et le hook est la méthode targetSquareLegal qui est definit par les sous classes pour adapter le comportement de chaque type de pièce.

# WEEK 6 : 
## HOMEWORK : 

Pas grand chose a dire mis a part les revisions pour les exams. J'ai pu relire les cours ou voir les vidéos et refaire les exercices afin de les enregistrer. 




