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


# MOULOUEL Tarik 

# COMPOSITE : 
- Composer des objets en structures arborescentes pour représenter des hiérarchies partie-tout
Le pattern Composite sert à modéliser des relations  partie-tout . Concrètement, on parle de relations où certains objets peuvent contenir d’autres objets, formant ainsi une structure hiérarchique en forme d’arbre.

    Exemple concret : un système de fichiers, où un dossier peut contenir d’autres dossiers et des fichiers.
    But : permettre une organisation claire de données ou de comportements, où un « composite » (par exemple un dossier) peut contenir d’autres éléments (dossiers et/ou fichiers).

- Le Composite rend facile l’extension de la structure en ajoutant de nouveaux types de feuilles (ou même de nouveaux types de composites, L’une des forces du pattern Composite est qu’il définit une interface commune (ou classe abstraite) pour tous les types d’objets : qu’il s’agisse d’un objet simple (une feuille, p. ex. un fichier) ou d’un conteneur (un composite, p. ex. un dossier). 

# VISITOR : 
- Le Visitor est un patron de conception (ou design pattern) qui permet de séparer la logique métier des opérations appliquées à une structure d’objets. Il repose sur le mécanisme de double distribution (double dispatch) pour faire en sorte qu’une opération s’applique correctement à chaque type d’élément rencontré. Voici un développement plus poussé sur ses avantages et ses inconvénients :
- Parmi ces avntages : 
    - Le mécanisme de double distribution garantit que l’opération adéquate est invoquée pour chaque type d’objet. Concrètement, on appelle d’abord la méthode accept sur l’objet (dispatch 1), qui ensuite appelle la méthode visitXxx appropriée sur le visiteur (dispatch 2). Cette propriété rend la collaboration entre le visiteur et les éléments visités très explicite et claire à suivre dans le code. le DP visitor a également des incovenients comme une faible adaptation aux évolutions structurelles :
# Mohamed Yassine Aloui
Dans le cadre de mon kata autour des échecs, j’ai poursuivi l’édition de la classe MyPawn (en particulier la méthode moveTo:) en recourant à l’héritage pour gérer la logique de déplacement spécifique des pions (dont l’en passant). Parallèlement, le patron Composite se révèle utile pour organiser des éléments en structures arborescentes (par exemple la hiérarchie Board → Square), et le patron Visitor (via le double dispatch) permettrait de séparer la logique métier liée aux différentes pièces, tout en facilitant l’ajout de nouvelles opérations. Cependant, Visitor s’avère moins flexible si la structure interne (types d’objets ou relations) change souvent, tandis que Composite simplifie l’extension de la hiérarchie en ajoutant de nouveaux types de « feuilles » ou de « composites ».