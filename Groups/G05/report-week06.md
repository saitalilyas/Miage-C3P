# WEEK 6 :

****
# KHADIJA BESBAS 

### Homework

Durant cette semaine j'ai continué à travailler sur mon kata.  J'ai bien avancé sur la partie "fonctionnel". Le pion qui peut effectuer la prise en passant à maintenant la bonne case qui peut être ciblé. Néanmoins, il me reste un problème à régler : 

<table border="1">
  <tr>
    <td style="width: 100px; height: 100px;"></td>
    <td style="width: 100px; height: 100px; text-align: center;"></td>
    <td style="width: 100px; height: 100px;"></td>
  </tr>
  <tr>
    <td style="width: 100px; height: 100px;"></td>
    <td style="width: 100px; height: 100px; text-align: center;">X</td>
    <td style="width: 100px; height: 100px;"></td>
  </tr>
  <tr>
    <td style="width: 100px; height: 100px;"></td>
    <td style="width: 100px; height: 100px; text-align: center;">Pion noir</td>
    <td style="width: 100px; height: 100px; text-align: center;">Pion blanc</td>
  </tr>
</table>

 

Le pion noir vient de faire un saut de deux cases. Le pion blanc peux donc effectuer la prise en passant et arrivé dans la case marqué d'une croix ( X ). Avec le code écris actuellement, mon pion noir n'est pas supprimé. Il faut donc que je trouve comment régler ce problème.
Comme je ne suis pas intérésser àla partie graphique, je vais continuer à me documenter pour comprendre comment est géré l'affichage.

Cette semaine j'ai aussi expliqué à d'autres élève ce que j'avais compris sur le problème de la  gestion de la prise en passant.

Enfin, j'ai lu les slides concernant le design pattern  *visitor* et le *double dispatch*.  

 
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

Cette semaine :
- J'ai travaillé sur mon kata
- Lu les slides
