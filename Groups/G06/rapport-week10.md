# Karim EL JISR 

## Polymorphisme, Évolution Logicielle et Recherche de Méthodes
Le polymorphisme est essentiel pour permettre l'évolution logicielle en rendant les objets interchangeables sans modifier le code existant. En langages dynamiquement typés, comme Pharo, le "duck typing" permet cette flexibilité naturellement : un objet peut jouer un rôle s’il comprend les méthodes nécessaires. Dans les langages statiquement typés, comme Java, les interfaces offrent une solution en définissant des contrats indépendants des hiérarchies de classes, facilitant l’ajout de nouvelles fonctionnalités sans altérer les structures existantes.

La recherche de méthodes repose sur le type dynamique d’un objet. Lorsqu’un message est envoyé, le système identifie la classe de l’objet, puis remonte sa hiérarchie pour trouver la méthode correspondante. Ce mécanisme garantit flexibilité et modularité, surtout dans un contexte polymorphe, en alignant le comportement avec le type réel de l’objet et non son type déclaré. En somme, le polymorphisme et la recherche de méthodes sont des outils clés pour concevoir des systèmes évolutifs et robustes. 


# MOULOUEL Tarik 

## TYPAGES STATIQUE ET DYNAMIQUE : 
 - Dans un langage à typage statique  : Les types sont vérifiés à la compilation. Cela signifie que le compilateur a besoin de connaître à l’avance le type exact de chaque variable ou paramètr 
 - Dans un langage à typage dynamique :
Les types ne sont vérifiés qu’à l’exécution. Concrètement, une variable peut changer de type au cours du programme. 

- Les objets polymorphes : un facteur clé pour l’évolution d’un logiciel Le polymorphisme désigne la capacité à appeler la même méthode ou fonction sur différents types d’objets, tout en obtenant un comportement spécifique à chaque type. Cette flexibilité est cruciale pour faire évoluer un logiciel sans nécessiter de réécriture massive. En effet, on peut ainsi ajouter de nouvelles fonctionnalités ou de nouveaux types d’objets tout en conservant le même code client.

- Le patron de conception Adapter illustre très bien le principe du polymorphisme : en créant un adaptateur qui fait le lien entre une classe existante et une interface cible, on rend les deux compatibles sans modifier la classe initiale. Cela montre comment on peut exploiter le polymorphisme pour adapter des composants hétérogènes, tout en maintenant une structure claire et évolutive.

