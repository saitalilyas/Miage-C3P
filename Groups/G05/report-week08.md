# WEEK 8:

****
# KHADIJA BESBAS 

### Homework



Cette semaine j'ai passé beaucoup de temps à chercher des solutions au bug soulevé lors de la présentation de mon kata.
En effet, deux problèmes ont été soulevé et que je n'avais jamais pris en compte : 
- Le joueur doit déplacer une pièce et a le choix parmi plusieurs pièces. Si la situation de "prise en passant" se présente, il peut choisir de l'effectuer ou non. S'il décide de déplacer une autre pièce sans effectuer la prise en passant, il ne pourra plus revenir sur sa décision. Ce n'était pas un problème auquel j'avais pensé. Je vais devoir ajouter un moyen de savoir quelle pièce a effectué le mouvement de deux cases (afin d'identifier la pièce qui vient d'être déplacée). Cette pièce ne pourra être considérée comme une cible pour la prise en passant que pendant un seul tour. Je pense donc qu'en ajoutant une gestion d'état du pion, je pourrais résoudre ce problème.
- Un pion qui n'a pas encore bouger peut avancer soit d'une case ou soit de deux. C'est déjà ajouter cette fonctionnalité, mais je n'avais pas penser au fait que une pièce se trouve devant le pion, il ne peux pas "sauter" au dessus et se retrouver sur la case d'après. J'ai donc réfléchis et je pense qu'ajouter une vérification concernant la case suivante devrais régler le problème.


J'ai continué ma reflexion concernant la refactorisation de mon code. Je ne sais pas encore quel design pattern utiliser pour la gestion des conditions sur la couleur de la pièce, mais les discutions en cours lors de la présentation du travails réalisé par chaque groupe m'a permis d'avoir des idées sur certain design pattern à utilier ( state, stategy ). 


Concernant le kata de promotion, j'ai continué à me documenter sur l'affichage. J'ai fais des petits exercices en essayant d'afficher un bouton sur une page blanche. J'ai eu des difficultés à me renseigner dessus, donc j'ai demandé un peu d'aide à des camarades de la classe.


Enfin, cette semaine relus les slides sur le visitor. Les explications en cours m'ont permis de mieux comprendre comment le visitor fonctionne, et quel est son intéret. Je réfléchis donc à l'utiliser dans mon kata aussi. 
De plus, j'ai aussi d'autres élèves sur leur kata.



****
# Cyril Godet

### Homework

Cette semaine, j'ai :
* essayé de trouver un moyen dans mon kata pour que le déplacement des pièces ne soit plus aléatoire.
  Mais je n'ai pas encore trouvé la solution. 
* Regardé les cours et les vidéos des points qui ont été abordés la semaine dernière:
  * le composite
  * le visiteur
  * le pattern state
  * double dispatch  
 Ceci m'a permis de faire une révision sur ces différents points. 
* Regardé les cours et les vidéos sur la partie sur l'héritage et sur la loi de Demeter

****

# BOU ALEXANDRE

Cette semaine :
- J'ai continué mon kata
- J'ai relue les pdf des 2 premières semaines.
