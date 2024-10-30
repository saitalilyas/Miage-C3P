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


