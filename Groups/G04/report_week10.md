## Lietard Evann
### Cours

Les types en programmation servent à indiquer quel genre d'objet une variable peut contenir. Le type statique est celui déclaré dans le code, et il ne change jamais.

Le type dynamique, lui, peut évoluer car il correspond à l'objet utilisé pendant l'exécution. Quand on appelle une méthode, le programme cherche dans la classe de l’objet pour voir s’il y a une correspondance, puis remonte si besoin dans les classes parentes. 

Le type statique aide à éviter les erreurs dès la compilation, mais il peut être moins flexible. 

Le type dynamique offre plus de liberté, mais cela peut rendre les erreurs plus difficiles à repérer.

 Dans les langages dynamiques, c’est simple : si un objet peut répondre à un message, ça marche, peu importe sa classe (c’est le "duck typing").
 
 Mais en langage statique, c’est plus compliqué, car les types sont stricts. 
 Les interfaces deviennent alors super utiles : elles permettent de définir ce qu’une classe doit faire sans imposer une hiérarchie. 
 Ça rend le code plus flexible et prêt pour des évolutions. 
 
### Kata

J'ai essayé de transmettre l'information du joueur directement aux pièces au lieu de la rechercher à chaque fois dans la classe Game.
Cependant, j'ai rencontré un problème : je n'arrive pas à initialiser cette information lors de la création des pièces, car elles sont toujours nulles.
Le problème semble venir du fait que la méthode où j'ai intégré ce comportement n'est tout simplement jamais appelée.
