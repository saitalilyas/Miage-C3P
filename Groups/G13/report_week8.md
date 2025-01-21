## Group 13: Week 8 report  
## SOLEIMANI 	SEPIDEH

I first watched “Avoid Null Checks” in the Module, it was really interesting, because I myself I’ve never thought about removing null checks and how to do it.
First, if it is possible in our API, we can think of returning an appropriate object which represents Null, like an empty collection or 0. 
But in some cases, we need to define our own Null Object based on the API, which contains all methods of our API, returning appropriate action.
EXample:
Tool Class with sous-classes: Creation, None, NotTool.
NotTool is our null object. So when we have : 

ToolPallette>>NextAction
	Self selectedtool attachedHandle

If that selectedtool is null, the attachedHandle which is defined as a method in null Object will be called and will do nothing.
So no need to have “ifNill”

## Composite:
Is a design pattern used to treat individual objects and composition of objects. A composite object contains multiple leaf objects.
Ex.
Component:   Graphic (declare our interface)
Leaf: text, Circle (represent object and define different behaviors using Polymorphic)
Composite: Diagram (defines behavior with children via polymorphic, stores child component and implement child-related operation)

## Visitor:
Represent an operation
Decouple this operation form the domain it applies to(so in order to have visitor we must have a domain first)
Support modularity
Support extension: means new visitors are easy to define without changing domain objects.

So Visitor+composite : A perfect match

Example:
We have a domain: Expression, sous-classes: Number and operation(which is a composite) who has sous-classes: Plus and Times.

Visitor: Expression Visitor, who has sous-classes Evaluator, Printer ( Print Polish Notation : +1*32  and InfixPrinter ( 1+(3*2))

We will define the method “acceptVisitor()” in each element of the composite which determines what to visit and in this way the right method will be called in the visitor.

So visitors will be able to evaluate all math operations and also print them in two different ways and it works with double dispatch basis.

For example in Visitor, in sous-class Evaluator, we have a method to evaluate plus as below:  
Evaluator >> visitPlus : aPlus
	| l r |
l := anExpression left acceptVisitor:self
r := an Expression right acceptVisitor:self
^ l+r

acceptVisitor: this method will again check what is on both sides of that plus to evaluate them appropriately.
