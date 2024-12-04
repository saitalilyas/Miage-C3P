*Auteurs : Guillaume GOOSSEN & Dimos MOUSSED-WERNITZ*

### Guillaume

#### Design pattern Visitor

Le Visitor permet d’ajouter de nouvelles opérations à une structure d’objets sans modifier les objets eux-mêmes. Chaque type d’objet (ex. `Plus`, `Times`, `Number`) accepte un Visitor via une méthode `acceptVisitor`. Le Visitor effectue alors l’opération en fonction du type d’objet grâce au double dispatch. Il devient complexe si la structure des objets change fréquemment.  

### Dimos  

#### Design pattern Composite  

Pour comprendre le Composite il faut simplement le voir comme un arbre composé de Feuilles et de Noeuds. Le Composite est là pour dire qu'un enfant (feuille) peut être noeud.  
Les feuilles font toutes quelque chose de différent mais avec la même API. Et offrent la même API que le Composite.  
L'avantage est que c'est extensible puisque c'est facile d'ajouter de nouvelles feuilles.  
C'est aussi la base pour les visiteurs.
