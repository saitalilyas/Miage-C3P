### Evann Lietard
#### Kata
La version 1 de mon kata est maintenant fonctionnelle. Toutes les méthodes principales ont été implémentées, et elles permettent d'exécuter les opérations de base du projet. Cependant, il reste encore plusieurs aspects à améliorer. D'une part, un refactoring est nécessaire pour rendre certaines méthodes plus efficaces et lisibles. D'autre part, bien que des tests de base aient toujours été effectués, les tests plus poussés doivent encore être développés pour assurer une couverture complète et détecter d'éventuels bugs.

Par la suite, je prévois également d'implémenter une version automatisée qui ne nécessitera pas d'intervention humaine pour certains choix
L'avancement du Kata peur etre vu içi: https://github.com/EvannLietard/Chess/tree/PawnPromotion

### PAWLOWSKI Florine 

#### Exercices 

J'avais déjà fait l'exercice Die & Die Handle lors de la semaine où nous avons découvert le dispatch (je ne savais pas que c'était du double Dispatch à ce moment là) 

https://github.com/PawlowskiFlo/Miage23/blob/2024/Groups/G04/report_week02.md

https://github.com/PawlowskiFlo/C3P/blob/main/week2/DieHandle.class.st

Pour m'entrainer je vais donc pouvoir appliquer le double dispatch sur mon kata. 
En fait dans les classe de type Piece les méthodes renderPieceOn appliquent déjà du dispatch en laissant la possibilité au Square de choisir la méthode qu'il souhaite utiliser. Pour retirer les blocks conditionnels dans les méthodes render de la classe Square je pense créer 2 sous classes BlackSquare et WhiteSquare, comme ça chaque classe connait déjà sa couleur et plus besoin de tester cette condition dans les méthodes render, cette implémentation me fait penser à la hiérarchie qu'on a vu dans le premier DS de pharo sur l'exercice du Train (le transport prend un passager en paramètre et le passager décide de la méthode de paiement à appliquer en fonction du type du paramètre). 

Ce qui m'embête un peu c'est que mes tests ne passeront plus si je change ça. Mais c'est normal que les set up des tests doivent changer, je ne vais plus créer des square et leur attribuer une couleur mais créer directement des WhiteSquare ou des BlackSquare. En soit les assert ne vont pas changer mais seuleument les set up. 

#### KATA 

https://github.com/EvannLietard/Chess/tree/refactor_piece_rendering/src

j'ai créé mes 2 sous classes MyWhiteChessSquare et MyBlackChessSquare. J'ai changé tous mes set up dans les tests que j'avais fait avant de faire du refactoring pour appliquer le double dispatch. Mes tests sont tous verts de nouveau. (sauf un test qui était basé sur la couleur que j'ai retiré puisque j'ai retiré la variable d'instance #color de MyChessSquare qui ne sert plus à rien avec l'implémentation des deux sous classes). 

On aurait pu faire la même chose avec les pièces, séparer en 2 sous classes de pièces : blanches et noires, mais je trouve que ce n'est pas forcément utile, on aurait beaucoup trop de classes et de méthodes à réécrire. Par exemple au lieu d'avoir une seule méthode renderBishop dans MyWhiteChessSquare on en aurait 2 en fonction du type de pièce passé (si la pièce est blanche ou noire). Si on regarde un peu plus loin dans l'évolution du projet et qu'on souhaite ajouter d'autres couleurs ce modèle ne serait plus du tout intéressant puisque beaucoup trop complexe. 

J'ai laissé plusieurs méthodes abstraites dans la classe MyChessSquare pour laisser d'autres implémentations possibles si par exemple on se retrouve avec un MyPinkChessSquare, la classe mère MyChessSquare impose la réécriture de ces méthodes abstraites et donc on garde le comportement 



