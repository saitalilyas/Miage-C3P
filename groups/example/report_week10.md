# ALLI Rayane - Week 10

## Méthode `open` - Implémentation du système de thèmes

Cette semaine, j'ai readapté la méthode `open` pour intégrer le nouveau système de thèmes visuels (SGSkin, SGClassicSkin, SGAppearance) dans la gestion des couleurs du jeu SameGame.

### Structure générale

La méthode crée une hiérarchie UI en trois étapes :

1. **Initialisation du plateau** : Création du modèle de jeu (`SGGame`) et du plateau graphique (`SGBoardElement`)
2. **Conteneur principal** : Un élément avec layout vertical qui accueille les sous-composants
3. **Panneau d'apparence** : Une barre de contrôle horizontale pour sélectionner les thèmes

### Panneau d'apparence

Le `appearancePanel` est structuré horizontalement avec un fond gris clair et contient trois éléments :

- **Étiquette "Skin: "** : Simple TextElement pour identifier le contrôle
- **Bouton Classic** : Fond blanc, angles arrondis, texte noir. Au clic, déclenche `SGAppearance currentSkin: SGAppearance classicSkin`
- **Bouton Dark** : Fond gris foncé, angles arrondis, texte blanc. Au clic, déclenche `SGAppearance currentSkin: SGAppearance darkSkin`

### Gestion des événements et couleurs

Chaque bouton dispose d'un gestionnaire `BlClickEvent` qui modifie le skin actif via `SGAppearance`. Cette approche centralise la gestion d'apparence : plutôt que de coder les couleurs directement dans `open`, le rendu récupère les couleurs du skin actif via l'interface SGSkin.

### Readaptation avec les nouvelles implémentations

La méthode a dû être entièrement refactorisée : les couleurs ne sont plus des constantes locales, mais des propriétés dynamiques fournies par le skin actif. Cela signifie que le code `open` communique uniquement avec `SGAppearance`, qui délègue ensuite aux skins (SGClassicSkin, etc.). Cette séparation garantit que ajouter un nouveau thème ne requiert pas de modification du code `open`.
