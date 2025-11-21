 # Rapport - Ait Ali Ilyas

 Cette semaine, j’ai analysé le nouveau projet SameGame pour comprendre comment il est construit. Le jeu utilise une architecture basée sur Myg, avec un plateau (SGBoard) et des cases (SGBox). Au lieu de créer une sous-classe pour chaque couleur, ils utilisent un design pattern Strategy : chaque case garde la même classe, mais change simplement d’état (la couleur). C’est plus propre et plus facile à gérer.


En étudiant tout ça, j’ai revu l’importance des design patterns et du polymorphisme, comme on l’avait fait en cours avec l’éditeur  et les exercices. Cela m’aide à mieux comprendre pourquoi ces concepts rendent un projet plus clair et plus facile à maintenir.



# Alli Rayane 
 j'ai commencé l'analyse de notre projet SameGame avant de pouvoir commencé l implementation de de ce dernier. Il etait ici question de se familiarsier avec les differentes restrcition comme poru la grille et la comprehension de l'architecture.Reperée les differents parten utilisé nottament celui pour les couleur ou il y aura forcement des possiblité d'amelioration. 