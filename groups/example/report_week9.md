
 # Rapport - Ait Ali Ilyas

Cette semaine, j’ai travaillé sur l’ajout d’une grille de taille variable dans le jeu SameGame. J’ai modifié la classe SameGame pour qu’elle puisse créer des plateaux personnalisés. J’ai ajouté une nouvelle méthode openWidth: height: pour définir librement largeur et hauteur.
J’ai adapté la création du plateau afin qu’il s’ajuste automatiquement aux dimensions données avec la méthode open qui a été conservée pour la compatibilité avec l’ancien fonctionnement.
Elle utilise maintenant la nouvelle fonctionnalité avec les valeurs par défaut.
Cette évolution rend le jeu plus flexible et prêt pour de futures améliorations.



# Rayane ALLI 

Cette semaine J’ai commencé à ajouter un système de thèmes visuels pour séparer la couleur logique de l’apparence affichée.
J’ai créé une interface SGSkin définissant un contrat clair : un skin doit fournir une couleur pour chaque type d’état (backgroundForBlueState, backgroundForRedState, etc.). 
Ensuite, j’ai implémenté SGClassicSkin comme skin par défaut, reproduisant l’apparence actuelle du jeu (bleu clair, rouge, vert, jaune, gris).
J’ai ensuite introduit SGAppearance, un gestionnaire central qui stocke le skin actif et peut annoncer SGSkinChangedAnnouncement lorsqu’on change de thème.