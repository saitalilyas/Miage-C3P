## DASSI-Helyana

# WEEK 10 :

## Partie avancement projet 

- Lancement du jeu, prise en main...

- j'ai analysé le code des packages afin d'obtenir une compréhension du rôle de chacun

- j'ai essaye de bien comprendre le but de mon kata, qui est de retirer un maximum de nil à l'aide du refactoring et du polymorphisme

- J'ai listé toutes les méthodes qui utilisent des nil pour comprendre si leur correspondance était une case vide ou inexistante afin de bien comprendre par la suite comment les remplacer

- Je me suis d'abord concentrée sur la partie des cases vides et réalisé les tests sur les cas où on utilise les méthodes 
qui exploitent les nil correspondant à une case vide, afin de bien conserver et ne pas modifier leur comportement

- J'ai ensuite créé une sous-classe qui hérite de MyPiece afin de gérer les cases vides

- J'ai remplacé les nil mais j'ai rencontré plusieurs difficultés et erreurs
Mes tests sont devenus rouges, ce qui est pour certains, normal, mais pour d'autres non ce qui m'a permis de constater que certaines méthodes avaient perdu leur comportement attendu
Il a fallu que je remplace les nil dans toutes les méthodes afin de pouvoir enfin jouer, car sinon, j'avais des erreurs en me disant ".." is nil


Ce qu'il reste à faire :

m'occuper de la partie testing et du code pour les cases inexistantes.



## HOMEWORK : 

Préparation à la présentation orale de nos katas 


## EL MANSOURI Yacine
# WEEK 10 :

### Cours 
Cette semaine on a vu les differents types, statique et dynamique et les interfaces.
Pour resumé en 2 point :  
- Le message en programmation suit deux étapes : recherche de méthode (dans la classe de l’objet récepteur, puis dans ses superclasses si nécessaire) et 
exécution de cette méthode. Les types influencent cette mécanique par leur nature statique 
ou dynamique. Les types statiques sont déclarés au moment de la compilation et ne changent pas, 
tandis que les types dynamiques dépendent de l’objet lié à l’exécution. La distinction est 
cruciale dans des environnements avec vérification de type, où seuls les messages valides 
peuvent être envoyés.

- Les objets polymorphes facilitent l’évolution logicielle, permettant à des objets d’interagir 
sans appartenir à la même hiérarchie. En langage dynamique, cette flexibilité repose sur le 
"duck typing" (un objet est compatible s’il implémente les méthodes nécessaires). 
En revanche, en langage statique, les interfaces définissent explicitement les types attendus. 

### Kata
J'ai continué a avancé sur le point "en passant" en reglant notamment les bugs au fur et à mesure.
