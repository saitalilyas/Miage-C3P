## DASSI-Helyana

# WEEK 9 :

## HOMEWORK : 
pas d'homework demandé



## exo fichier composite/visitor

J'ai ensuite implémenter l'exercice sur les fichiers avec Visitor : 
 cf photo partie sur l'implémentation avec Visitor : 
![VISITOR FILE](visitorfile.png)

## Partie projet 
Je me suis d'abord concentrée sur les méthodes où les nil représentent des correspondances avec les cases vides, 
laissant pour l'instant la gestion des cases inexistantes de côté.


## EL MANSOURI Yacine
# WEEK 9 :

### Cours
Cette semaine on a etudié les differences entre délégation, héritage et conditions. 
Chacune de ses solutions comporte ces avantages et ces incovenients.
#### Solution avec héritage
Chaque algorithme de formatage est encapsulé dans une sous-classe.
- Avantages :
Modularité : les algorithmes sont isolés dans des classes distinctes.
Facilité d’ajout d’algorithmes via sous-classement.
- Inconvénients :
Difficulté de changement dynamique d'algorithme.
Explosion combinatoire de sous-classes pour gérer des fonctionnalités multiples.
Alourdissement de l’API du parent avec des responsabilités croisées.
#### Solution avec des conditionnels
Une seule classe gère tous les algorithmes, sélectionnés à l'exécution.
- Avantages :
Permet un changement dynamique d’algorithme.
- Inconvénients :
Ajout coûteux : nécessite modification et recompilation du code.
Manque de modularité : difficile de déployer de nouveaux algorithmes isolément.
#### Solution avec délégation
L’éditeur délègue le formatage à des objets "formateurs".
- Avantages :
Grande flexibilité pour changer ou étendre les algorithmes.
Modularité : les formateurs sont bien isolés.
Simplification de l’API principale grâce à une séparation des responsabilités.
- Inconvénients :
L’éditeur doit exposer son état pour permettre aux formateurs de travailler, ce qui peut affaiblir l’encapsulation.

### Kata
J'ai commencé à reflechir pour le dernier point de mon kata, notamment le mouvement "en passant". 
J'ai alors compris qu'il fallait que j'enregistre le dernier mouvement de la partie pour que le mouvement soit possible qu'une seul fois apres 
le mouvement de 2 cases par le pion adverse et non pas tout le temps. Pour cela j'ai decidé de créer une classe pour contenir le mouvement
avec la piece, avec laquelle j'itiniliserai une instance dans la classe game.






