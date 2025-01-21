# AIT YAHIA Maya 

## Design pattern Composite :

Cette semaine, j'ai regardé les vidéos sur le design pattern Composite, qui permet de structurer des objets en hiérarchies. 
Par exemple, dans un diagramme, chaque élément (texte, cercle, segment) peut être un objet individuel ou un groupe d'objets (composite). 
Tous ces objets, qu'ils soient simples ou composites, partagent une même interface, permettant de les manipuler de manière uniforme. 
Cela simplifie l'ajout de nouveaux comportements sans modifier la structure existante.

## Kata (les mouvements des pions): 

J'ai refactoré ma méthode targetSquareLegal, qui gérait avant tous les mouvements, en appelant maintenant des petites méthodes dédiées à chaque type de mouvement. 
Cela permet d'éviter une méthode trop longue et complexe, remplie de nombreuses conditions if. 
J'ai également commencé à réfléchir à la manière d'implémenter le dernier mouvement "en passant".

# Dahouane Youssra

## Kata (Refactorisation du rendu des pièces)

1.	Création des méthodes de rendu :
   
J’ai ajouté des méthodes dans les classes MyBlackChessSquare et MyWhiteChessSquare qui renvoient les caractères appropriés pour chaque pièce (renderWhiteBishop, renderBlackKnight, renderWhiteKnight, etc). 

2.	Modification de initializeSquares dans MyChessBoard :
   
J’ai remplacé les références aux couleurs noir et blanc par mes deux nouvelles classes MyBlackChessSquare et MyWhiteChessSquare.

3.	Modification de initialize dans MyFenParser :
   
J’ai modifié le dictionnaire pour associer chaque symbole de pièce à sa couleur et à sa classe appropriée.

4.	Tests :
   
J’ai écrit des tests pour vérifier que les bons caractères correspondant à chaque pièce s'affichent correctement en fonction de la couleur de la case et de la pièce.


# COUNDOUL Adama

## Kata (Promotion du pion)

1. Work Done:
   
Implemented moveToInteractiveVersion:

- Added a feature to let the user promote a pawn when it reaches the last rank.
- Created a dialog box where the user can choose between "Queen," "Rook," "Bishop," or "Knight."

2. Next Steps:

- Write Tests:

Test the promotion feature in different situations (valid choices, closing the dialog without choosing, promotion on the first and last ranks, etc.).
Make sure promotion works for both black and white pawns.

- Fix Screen Opening:

Make sure the dialog box opens directly on top of the game interface.
Use tools that work with Pharo 12, like Blocs and Toplo .

- Refactor the Code:

Make the code easier to read and improve its structure.
Create a separate method for making promoted pieces.

- Merge the promotion feature with the rest of the game.
  
Fix any problems that come up when merging the code.




