## Evann Lietard
### Cours
Le design pattern composite permet de manipuler des objets individuels (feuilles) et des groupes d’objets (composites) de la même façon, en utilisant une interface commune.

Par exemple :

Une feuille est un élément simple, comme un fichier dans un dossier.

Un composite est un groupe d’éléments, comme un dossier qui contient des fichiers et d’autres dossiers.

Avec le composite, tu peux parcourir toute la structure sans te soucier si tu as affaire à un élément simple ou à un groupe.

### Kata
J'ai refactoré mon code en appliquant le design pattern Strategy pour gérer la promotion des pions dans mon jeu d'échecs. J'ai créé la classe MyManualPromotionStrategy subclass du classe abstraite, qui contient la logique de promotion manuelle des pions, y compris la création des boutons pour chaque type de pièce (Reine, Tour, Fou, Chevalier) et la gestion de la fenêtre d'affichage. J'ai également modifié la classe MyPawn et Myplayer pour intégrer cette nouvelle stratégie, déléguant ainsi les responsabilités de promotion à la stratégie appropriée. Enfin, j'ai ajusté des tests pour valider le bon fonctionnement de la stratégie, en m'assurant que les boutons sont créés correctement et que les pièces sont remplacées comme prévu. La stratégie de promotion manuelle est maintenant terminée et fonctionne comme attendu.
