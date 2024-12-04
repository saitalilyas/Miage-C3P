## DASSI-Helyana

# WEEK 7 :

## HOMEWORK : 
 

# VISITOR 

Le pattern Visitor permet de séparer des opérations d’un ensemble d'objets sans modifier leur classe, il introduit un objet visiteur qui va effectuer des des opérations spécifiques sur ces objets.
Ajouter de nouvelles opérations  = ajouter de nouveaux visiteurs toujours sans toucher aux classes

### VISITOR et DOUBLE DISPATCH

Le Visiteur utilise le double dispatch, à chaque objet du domaine de spécifier la manière dont il doit être visité par un Visiteur.
Le double dispatch est essentiel pour gérer les visites.

### Quand l'utiliser

Le pattern Visitor est utile quand on doit appliquer plusieurs opérations différentes sur des structures d'objets


## EL MANSOURI Yacine

### Double dispatch
Cette semaine on a decouvert le double dispatch, que j'ai exercé sur l'exercice "pierre papier ciseaux".

### Visitor
J'ai également lu les slides sur le pattern visitor dont j'ai fais ressortir quelques points principaux :

- Objectif du pattern Visitor :
Le Visitor est un patron de conception qui permet de séparer des opérations d'une structure d'objets.
Utile pour appliquer différentes actions sur des objets sans modifier leurs classes de base.

Exemple :
Dans un exemple de système d'expressions arithmétiques (comme dans le cours), le Visitor permet de gérer des opérations comme l'évaluation ou l'impression d'expressions (ex. : 1 + (3 * 2)).
Plutôt que de mettre les comportements directement dans les classes d'expression (comme Plus, Times, Number), ils sont délégués à des visiteurs, comme Evaluator ou Printer.

Structure du Visitor pattern :
Les classes d'expression (par exemple, Plus, Times, Number) implémentent une méthode acceptVisitor:, qui permet de déléguer le traitement à un Visitor spécifique.
Chaque Visitor possède des méthodes spécifiques pour chaque type d'expression, comme visitNumber:, visitPlus:, visitTimes:, etc... pour exécuter les opérations appropriées.

Double dispatch :
Le Visitor pattern repose sur le double dispatch, qui permet à l’objet d’expression de déléguer le choix de la méthode exacte à appeler à l’instance de Visitor.
Cela évite les vérifications conditionnelles, car chaque classe sait comment elle doit être visitée.

Quand utiliser le Visitor pattern :
Le Visitor pattern est recommandé pour des opérations multiples sur des structures d’objets qui sont stables et peu susceptibles d'être modifiées fréquemment.
