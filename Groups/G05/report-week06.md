# WEEK 6 :

****
# KHADIJA BESBAS 


****
# Cyril Godet

### Homework

Cette semaine, j'ai :
* travaillé sur le double dispatch, notamment en réalisant l'exercice avec pierre, feuille, ciseaux.
* travaillé sur le projet. Je me suis rendu compte que je n'étais pas parti dans la bonne partie du code pour réaliser mon kata.
En approndissant mes recherches, je me suis rendu compte que la protection du roi intervenait lorsque le joueur joue.
C'est donc dans la méthode play de la classe MyPlayer que j'ai decidé d'intégrer la logique de protection du roi. A savoir :
  *  Si le roi est en échec alors, existe-t-il une pièce qui peux capturer la pièce qui menace le roi ?
  *  ou existe-t-il une pièce qui peux bloquer la pièce qui menace le roi ?
  *  Sinon on concerve la logique existante, c'est-à-dire que le roi doit se déplacer s'il le peut
 
  J'ai aussi réalisé 3 méthodes de test pour les différents cas ci-dessus mais je n'ai pas encore compris comment désigner si une pièce est dans une case dans mes assertions.  
  Par ailleurs, comme j'ai modifié la méthode play de la classe MyPlayer. Celle-ci est maintenant très grande, il va falloir que je l'optimise avec du refactoring.


****

# BOU ALEXANDRE
