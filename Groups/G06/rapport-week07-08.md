# Karim EL JISR 

## Composite : 
Le design pattern Composite est une solution pour composer des objets en structures arborescentes, 
permettant de représenter des hiérarchies partie-tout tout en offrant une API uniforme pour les feuilles (objets individuels) 
et les composites (objets avec enfants). Les principaux participants sont : le composant, qui définit l'interface commune ; 
les feuilles, qui implémentent un comportement spécifique sans enfants ; et les composites, qui gèrent les enfants et implémentent 
des opérations communes.

Ce pattern est extensible, supporte le polymorphisme et s'intègre bien avec d'autres patterns comme Visitor et Factory. 
Il est particulièrement utile pour manipuler de manière uniforme des structures complexes comme des documents ou des diagrammes 
tout en facilitant l'ajout de nouveaux types d'éléments.

## Visitor :
Le pattern Visitor permet de définir des opérations sur des objets sans modifier leurs classes, 
en séparant le comportement de la structure. Il introduit un visiteur qui applique les opérations en fonction des types d'éléments 
(par exemple, Number, Plus, Times) et utilise la double dispatch pour éviter les conditions complexes. 
Les objets acceptent le visiteur via acceptVisitor, qui appelle la méthode appropriée du visiteur (visitNumber, visitPlus, etc.), 
favorisant ainsi l'extensibilité et la modularité. Ce pattern est idéal pour des graphes d'objets structurés nécessitant plusieurs 
opérations (évaluation, impression), mais devient moins pratique si la structure des éléments change fréquemment.