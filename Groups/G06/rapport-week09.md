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


# MOULOUEL Tarik 

- L’héritage permet aux développeurs de prendre une classe existante (la superclasse) et de créer une nouvelle classe (la sous-classe) qui ajoute de nouveaux attributs (c’est-à-dire l’« état » de l’objet) et qui hérite ou redéfinit certaines méthodes (le « comportement »).

- Une seule superclasse :
La plupart des langages qui utilisent un modèle d’héritage simple imposent qu’une classe n’ait qu’une seule superclasse directe. Par exemple, en Java, une classe peut « extends » une seule autre classe, mais peut implémenter plusieurs interfaces.

- Héritage ultime depuis Object :
Dans certains langages, comme Java ou C#, toute classe hérite en fin de compte d’une classe racine nommée Object. Cela signifie que toutes les classes partagent des méthodes et des propriétés fondamentales (comme toString(), equals(), etc. en Java).

Héritage de l’état statique :
L’état, représenté par les attributs ou les champs de la classe, est considéré comme hérité de façon « statique ». Autrement dit, il est défini au moment de la compilation et est lié directement à la structure de la classe. Quand on instancie une sous-classe, celle-ci dispose également de tous les attributs (état) hérités de la superclasse.

Héritage du comportement dynamique :
Le comportement, quant à lui, se réfère aux méthodes et fonctions de la classe. L’héritage de comportement est qualifié de « dynamique » parce que l’exécution d’une méthode (redéfinie ou non) est résolue à l’exécution grâce au mécanisme de liaison tardive (dynamic dispatch). Cela permet de déterminer automatiquement la bonne méthode à appeler selon le type effectif de l’objet en mémoire (polymorphisme).
## Mohamed Yassine Aloui
La délégation et l’héritage offrent deux approches distinctes pour structurer le code : l’héritage s’appuie sur des relations statiques (sous-classes qui héritent ou redéfinissent l’état et le comportement de la superclasse), tandis que la délégation repose sur la coopération dynamique d’objets (design pattern Strategy, par exemple) pour davantage de modularité.