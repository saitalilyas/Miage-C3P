# WEEK 10:

****
# KHADIJA BESBAS 

### Homework

Cette semaine j'ai continué à travailler sur mon kata. J'ai réglé le bug qu'il me restait. Maintenant, lorsqu'un joueur déplace une autre pièce à la place de faire la prise en passant, il ne pourra plus le faire au tour d'après.
J'a ajouté le pattern stratégie: toutes les pièces ont une stratégie de mouvement. Si elles sont noir elles vont vers le bas et si elles sont blanches elles vont vers le haut. 
J'ai utilisé cette gestion de la stratégie que sur le pion, mais je pense qu'elle pourrait être  généralisé aux autres prèces.
J'ai aussi ajouté un visiteur pour pouvoir visiter la pièce ciblé ( dans le cas du mouvement en passant ), et adopter un comportement suivant son état. Par exemple si la pièce visité est une pièce qui vient de se déplacer de deux case, son état est "double avancé". Le visitor  va donc permettre de ciblé la case de la "prise en passant".

J'ai continué à travailler sur le kata concernant la promotion. J'ai notemment cherché à savoir comment detecter qu'un utilisateur ferme la fenêtre. Le but est que dans ce cas, lors de la promotion, le choix sera un choix par défault.


****
# Cyril Godet

### Homework

Cette semaine, j'ai :
* Regardé les poly de cours sur les types. En particulier sur la diiférence entre les types statiques et dynamiques au moment de la création d'un objet.
* Avancé sur mon kata. J'ai appliqué le principe de refactoring en simplifiant ma méthode play avec l'aide du design pattern Chain of Responsibility qui me permet de pouvoir ainsi créer une logique d'enchaînement:
 1. Lorsque le roi est un échec on essaye d'effectuer d'abord la capture puis le blocage et le déplaacement du roi
2. Sinon on concerve le déplacement pardéfaut : une pièce aléatoire se déplace

Tous les tests que j'avais créer pour respecter les contraintes de déplacement sont maintenant verts.  
Il ne me reste plus qu'à faire la partie déplacement "manuel" du joueur sur l'échiquier.
  
**** 
# BOU ALEXANDRE
