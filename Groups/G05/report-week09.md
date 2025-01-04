# WEEK 9:

****
# KHADIJA BESBAS 

### Homework

 Cette semaine j'ai avancé sur mon kata. J'ai réglé le bug qui concernait le fait que le pion ne doit pas pouvoir avancer de deux cases si la première case contient déjà une pièce. 
 Concernant l'autre bug qui avait était relevé lors de la présentation de mon kata à la classe, je n'ai pas trouver encore comment le régler. Je continue donc de chercher un moyen de pouvoir savoir si un joueur à choisis  de déplacer une autre pièce à la place du pion pouvant faire la prise en passant.
 J'ai refactorisé mon code en ajoutant une gestion avec un état: 

```
Etat initial ------> Etat avancée double 
        |                   |
        |                   |
        -------------> Etat en mouvement     
```

J'ai aussi réfléchis à une solution pour ne plus avoir à vérifier la couleur de mon pion pour savoir si il doit aller vers le haut ou le bas. Je pense à utiliser le pattern strategy mais je ne sais pas encore comment le faire.



****
# Cyril Godet

### Homework

Cette semaine, j'ai avancé sur mon kata.  
En particulier, j'ai enfin pu terminer ma méthode play.  
Ce qui permet de pouvoir lorsque l'on clique sur le bouton play de respecter la logique de mon kata.
C'est-à-dire soit: 
* le roi est en échec et une pièce peut capturer la pièce qui menace le roi.
* le roi est en échec et une pièce peut bloquer la pièce qui menace le roi.
* le roi est en échec et aucune pièce ne peut ni capturer ou bloquer la pièce qui menace le roi. Donc le roi se déplace.
* le roi n'est pas en échec alors une pièce aléatoire se déplace.

J'ai par ailleurs ajouté une quatrième méthode de test pour prendre en compte
le cas où il n'y a pas d'échec, même si le déplacement est aléatoire.  
J'ai donc réalisé mon test avec deux pièces, ce qui fait que dans ce cas au moins une pièce a bougé.

Pour mon kata, il me reste donc à faire :
* simplifier ma méthode play en utilisant du refactoring. Ce que j'ai déjà un peu commencé à faire.
* adapter le mécanisme de mon kata pour qu'il puisse être appliqué lorsque le joueur décide de jouer de façon "manuelle".
C'est-à-dire lorsque le joueur déplace une pièce avec sa souris. 
  

# BOU ALEXANDRE
