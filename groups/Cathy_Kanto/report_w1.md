KENGLE NKOUAMEN Pierrette Cahty
        Les collections en Pharo et leurs itérateurs

            Une collection en Pharo est un objet qui regroupe d’autres objets. Elle sert à stocker, organiser et manipuler des ensembles de données.

            Types de collections fournies par la bibliothèque standard :

                OrderedCollection : liste dynamique (ajout/suppression flexible).
                Array : taille fixe, accès rapide par index.
                Set : ensemble sans doublons.
                Dictionary : associations clé → valeur.
                SortedCollection : collection triée automatiquement selon un critère.

            En Pharo, l’itération se fait par envoi de messages.
            
                Différence principale :

                do: exécute une action (effet de bord).
                collect: transforme la collection.
                select: filtre selon une condition.

        Les conditionnels en Pharo

            Pharo n’a pas de mot-clé if comme en Java ou Python. Ce sont les booléens eux-mêmes qui reçoivent les messages ifTrue: ou ifTrue:ifFalse:.        

            Différence avec d’autres langages :

            Ici, le booléen est un objet qui sait quoi faire quand on lui envoie ifTrue:.
            On n’évalue pas une “structure de contrôle” mais on envoie un message.

            Avantages :
                - Plus orienté objet.
                - Plus flexible (on peut redéfinir des comportements).

            Inconvénients :
                - Déconcertant pour les débutants.
                - Peut sembler verbeux par rapport à if ... else.

        Création de classes et méthodes

            Classe Simple:
                Object subclass: Person
                instanceVariableNames: 'name age'
                classVariableNames: ''
                package: 'MyApp'.
            
            Méthodes :
                Person >> name
                ^ name

                Person >> name: aName
                name := aName

                Person >> age
                ^ age

                Person >> age: anAge
                age := anAge
        

            Exemple de programme simple

                p := Person new.
                p name: 'Alice'; age: 25.
                Transcript show: p name , ' a ' , p age printString , ' ans.'; cr.
        

            Problèmes rencontrés :

            Au début, j’avais du mal à comprendre que la définition des classes se fait via l’IDE (System Browser) et non dans un fichier source classique.
            J’ai dû m’habituer à la navigation dans l'IDE.

        Style de code Pharo

            Règles courantes :
                Méthodes courtes (une dizaine de lignes maximum).
                Noms de méthodes clairs, souvent verbe + complément (addPerson:, findByName:).
                Classes regroupées en packages bien nommés.
                Eviter les variables temporaires inutiles.

            Outils de style :
                Pharo fournit un Critic Browser qui signale les violations des règles de style.

        Extras – Cascades et Block Closures

            Cascades (;)
                Permettent d’envoyer plusieurs messages au même objet sans répéter son nom :
                Exemple:
                    p := Person new
                    name: 'Alice';
                    age: 25;
                    yourself.

            Block closures ([ ])
                Ce sont des fonctions anonymes. Utilisées pour :
                    - Itérations (do:, collect:, …)
                    - Conditionnels (ifTrue: [ ... ])
                Exemple:
                    factorial := [ :n | 
                    n = 0 ifTrue: [ 1 ] ifFalse: [ n  (factorial value: n - 1) ] ].

                    Transcript show: (factorial value: 5) printString; cr.
    



KANTO....
