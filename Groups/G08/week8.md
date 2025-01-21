## DASSI-Helyana

# WEEK 8 :

## HOMEWORK : 
 

## COMPOSITE:



### Quel est son but ?

Le but principal de ce design pattern est de créer une hiérarchie d’objets (comme un arbre) où chaque élément, qu’il soit simple (une feuille) ou composé, partage une interface commune. 

feuille = sans enfants 
compose = peut ajouter ou supp des enfants


Le Composite utilise le polymorphisme pour permettre au client d'interagir avc des objets de manière uniforme, sans avoir à vérifier leur type ou leur structure interne

ex: 
systèmes de fichiers :
- Un fichier est une feuille.
- Un dossier est un composé pouvant contenir des fichiers ou d’autres dossiers.

## EL MANSOURI Yacine
# WEEK 8 :
## HOMEWORK :

Cette semaine on a pu aborder les designs paterns qui sont des solutions récurrentes à des problèmes de conception que beaucoup de gens ont pu croiser. Plus particulierement on a decouvert le patern Composite et Singleton. Donc chaque design patern permet de repondre à un probleme de conception.

- Composite : Il permet de composer des objets en structures arborescentes pour représenter des hiérarchies "part-whole". Pour cela il permet aux clients de traiter les objets individuels et les compositions d'objets de manière uniforme. Tout ca grace au polymorphisme. Les feuilles implémentent des comportements spécifiques tandis que les composites délèguent aux enfants. 

- Singleton : Il assurez qu'une classe n'a qu'une seule instance et fournis un point d'accès global à celle-ci. Il agit un peu comme une variable globale déguisée. Ca peut être utile pour des ressources uniques, comme une connexion à une base de données.



