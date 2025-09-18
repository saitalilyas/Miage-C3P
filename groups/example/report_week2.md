# Report - Alli Rayane

L'objectif de ce travail était d'explorer le mécanisme de "message dispatch" en Pharo. Dans ce langage tous est message, ce qui rend le dispatch  dynamique. Ce dernier vas directement recuperée la methode associé au message afin de lui appliquée, dans certains cas comme avec l'heritage il sera question de lookup pour attribué la bonne methode. Cest ce que nous allons testé dans nos petits blocs de codes.


## Rédigez de petits exemples de code mettant à l’épreuve vos connaissances en matière de répartition.  
```
Object << #Véhicule
    slots: {}
    package: 'MonExemple'

pneu
^ nb de pneu inconnu 


Véhicule << #Voiture
    slots: {}
    package: 'MonExemple'
pneu
^ nb de pneu égale à 4



Véhicule << #moto
    slots: {}
    package: 'MonExemple'
pneu
^ nb de pneu égale à 2




Véhicule << #camion
    slots: {}
    package: 'MonExemple'
pneu
^ nb de pneu égale à 16
```


```
"Création des objets"
| uneVoiture uneMoto unCamion  |

uneVoiture := Voiture new.
uneMoto := Moto new.
unCamion := Camion new.

Transcript show: 'À uneVoiture : ', uneVoiture pneus; cr.
Transcript show: 'À uneMoto : ', uneMoto pneus; cr.
Transcript show: 'À unCamion : ', unCamion pneus; cr.
```

```
"resultats"
À uneVoiture: nb de pneu égale à 4
À uneMoto: nb de pneu égale à 16
À unCamion: nb de pneu égale à 16
```

## Est-ce que les exemples ont fonctionné comme prévu ?
Oui, les résultats observés correspondent a ce que j'avais compris avant l'experimentation de mon heritage de vehicules. Cela etant comparable au polymorphisme en java , ces dernier partagent des similitudes .

## Qu’y avait-il de différent entre ce à quoi vous vous attendiez et ce que vous avez vu dans la réalité ?
Ayant une approche tournée vers l'objet il m'as fallut bien comprendre le principe de message en pharo pour pouvoir faire la bonne distinction entre les deux. Concretement il n'y a pas d'appel de methode seulement des messages envoyés.

## Comment pouvez-vous corriger vos hypothèses et comment avez-vous trouvé cette information ? 
Mes hypothèses de departs etait au final correct. Seulement cette exercice ma bien fais comprendre la difference entre les objects classqiues en des autres langages et les messages en pharo.