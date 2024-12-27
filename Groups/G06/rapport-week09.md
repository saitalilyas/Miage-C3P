# Kaeim EL JISR 

## Délégation vs. Héritage

Objectifs du cours :

- Comparer les conceptions basées sur la délégation et celles basées sur l'héritage.

- Introduire des critères pour évaluer ces approches.

* Approche par héritage : Créer des sous-classes spécifiques pour chaque type de mise en forme. 

* Approche par conditionnelles : Utilisation de sélection dynamique via des structures conditionnelles. 
Avantages : flexibilité pour changer d'algorithme. 

* Approche par délégation : Délégation des opérations à des objets formatteurs spécialisés (design pattern Strategy). 
Avantages : modularité, flexibilité à l'exécution. 

### Conclusion :

L'héritage permet de définir des abstractions statiques mais manque de flexibilité, tandis que la délégation favorise la modularité et la flexibilité à l'exécution. Le choix entre les deux dépend des besoins en termes de maintenance et évolutivité. Cependant, aucune approche n'est sans compromis.


## Avancement sur le projet d'échecs
Sur l'avancement du projet d'échecs , je suis entrain de faire des tests sur la promotion des pions black et white aux deux extremités du board et j'ai crée la methode promote qui permet au pion dès qu'il arrive à l'extremité du board de pouvoir faire une promotion .