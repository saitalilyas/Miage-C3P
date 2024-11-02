## Group 13: Week 7 report  
## SOLEIMANI 	SEPIDEH

I started to learn double dispatch and how it is supposed to be implemented in Pharo. I even understood where and when the double dispatch is meant to be implemented.
Such a great solution in cases where there are so many ifTrue and ifFalse.
So the key in double dispatch is to define classes for both sides and methods in each class, so when we send one as a message to another class, the appropriate method will be executed and we will get rid of all conditionals in this way.
I practiced it with the implementation of rock paper scissors as I will put you the link in this report.

https://github.com/sepideh94/C3P_week6

As I work on same Kata in Chess game, so it was essential for me to understand how does double dispatch works exactly, so I will be able to implement this method on renderpiece in Chess in order to avoid all conditionals.
It is not yet all clear for me the steps of this Kata with details, but I already started to think and plan what should be done.
First I suppose I should have Black and White subclasses for all piece, like BlackBishop and WhiteBishop, then the same thing with squares and then I must define methods which return the appropriate letter. But what sounds like a problem in my mind is that in the game, all pieces and square are instances of the main classes then a color is going to be attributed to them. 
So my question is should I modify the core of the coding in the game and make instances of my defined classes? Is it possible to modify codes without disturbing the functionality of the game?
