# AIT YAHIA Maya 

Cette semaine en cours, nous avons étudié les concepts de Template Method et de Hooks en programmation orientée objet. Ces modèles permettent de structurer un algorithme général tout en laissant aux sous-classes la possibilité de redéfinir certaines étapes spécifiques.

## Template Method
La Template Method est une méthode dans la superclasse qui définit les étapes générales d'un algorithme. Elle fixe une structure commune tout en déléguant certaines étapes aux sous-classes.

## Hook
Un Hook est une méthode dans la superclasse, souvent vide ou avec un comportement par défaut. Il peut être redéfini dans les sous-classes pour adapter l’algorithme à des besoins spécifiques.

## Exemple dans le projet d’échecs
Dans le projet d’échecs, on retrouve ces concepts dans la méthode targetSquare. Elle agit comme une Template Method qui définit la logique générale pour cibler une case. La méthode targetSquareLegal est utilisée comme un Hook et redéfinie dans chaque sous-classe pour adapter le comportement de chaque type de pièce.

# Dahouane Youssra 

## Homework 

### Template Method

Template Method est un design pattern qui définit la structure d'un algorithme dans une méthode de la superclasse, tout en déléguant certaines étapes spécifiques aux sous-classes. Ce pattern facilite la réutilisation du code et permet des personnalisations sans changer la structure globale de l'algorithme.

### Hooks

Les hooks sont des méthodes définies dans la superclasse qui peuvent être réutilisées ou personnalisées par les sous-classes. Elles permettent à ces dernières d'intervenir à des points spécifiques de l'algorithme défini par Template Method.

### Exemples 

Dans le chapitre 11 du MOOC, les classes EAddition et EMultiplication avaient chacune une méthode printOn presque identique, qui se distinguait uniquement par l'opérateur utilisé (+ pour EAddition et * pour EMultiplication). Pour éviter cette duplication de code, une superclasse, EBinaryExpression, a été créée. Elle contient une méthode printOn qui sert de template method, et définit la structure générale de l'affichage des expressions. Cette méthode appelle un hook, que chaque sous-classe (EAddition et EMultiplication) doit implémenter pour fournir son propre opérateur.

Dans le projet d'échecs, un exemple pertinent est la méthode targetSquare, qui agit comme un Template Method pour déterminer les cases cibles possibles pour chaque pièce. Elle utilise le hook targetSquareLegal, que chaque sous-classe (comme MyPawn, MyRook ou MyKing) redéfinit pour adapter la logique de mouvement de chaque type de pièce. 

# COUNDOUL Adama

## Look in the chess game for template methods

 A template method specifies a skeleton with hooks. Hooks are places to be customized by subclasses.
 
### How can you identify them?

By checking the class hierarchies and look about methods in the abstract class who call another (hook) methods which is defined in the subclasses. A template method sets the context
 Hooks specify variations.

 ### Example in the Chess Game 
 
```
 targetSquares
	^ self targetSquaresLegal: false
```

This method is a template method because she calls a hook method targetSquaresLegal which is defined in each sublasses.



 


