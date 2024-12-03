## Group 13: Week 9 report  
## SOLEIMANI 	SEPIDEH
# Inheritance and Delegation in Pharo

I watched the related videos i the module, I understand it via the elaborated example:

# Scenario: Managing a text editor (TextEditor).
# Objective: Add text formatting algorithms.

# 1- Using Inheritance:
Create a class hierarchy with a main TextEditor class and create specific subclasses like FastFormatEditor, SlowFormatEditor, NullFormatEditor and  … for each formatting algorithm.
Pros: Addition and Packaging
Cons: Not possible to dynamically switch because we have to crest the right text editor at the beginning.

# 2- Using conditions: One class with all formatting algorithms as methods.
Pros: Not possible to dynamically switch because we have to crest the right text editor at the beginning.
Cons: Addition and Packaging

# 3- Using Delegation(reference):
TextEditor delegates formatting to an external object like Formatter.
Pros: Allows dynamic addition or modification of formatting algorithms. Promotes modularity and code reuse(packaging).
Cons: formatter should have access to the state of the text so the API should be open to support it.

## Coupling Law of Demeter 
To avoid a wave of changes whenever we change sth in a class that other classes are sending messages to, we should use encapsulation.
Means according to law of Demeter we are not allowed to send messages to the mathodes hat are defined in other classes as a chain.
# ex: 
Source >> do
dependent indirectDependent dosomething: text
In this way whenever we change sth in Indirectdependent we should change source as well.

# Solution:
Step1: Source >> do
           dependent.depDo()
Step 2: Dependent >> depDo
 	        indirectDependent.inDepDo()
Step3: IndirectDependent >> inDepDo
	        dosomething: text
     
# In this way single changes won’t end up to a wave of change.
