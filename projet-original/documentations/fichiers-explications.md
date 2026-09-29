# Explications du projet
## Présentation
Notre projet consiste à réaliser un convoyeur automatisé capable de trier des objets selon leur poids.
Le système transporte les objets sur un convoyeur. Un capteur infrarouge détecte leur présence, puis une balance mesure leur poids. L'Arduino analyse ensuite cette mesure afin de déterminer la catégorie de l'objet. Un mécanisme de tri permet finalement de diriger l'objet vers le bac correspondant.
Le système utilise également un écran tactile pour afficher les informations sur l'objet et l'état du système.
## Fonctionnement général
Lorsque le système est mis en marche, le convoyeur transporte les objets vers la zone de détection. Le capteur infrarouge détecte lorsqu'un objet arrive. Son poids est ensuite mesuré par la balance.
À l'aide du microcontrôleur, on récupère la mesure du poids et détermine la catégorie de l'objet selon les seuils définis. Le mécanisme de tri déplace ensuite l'objet vers le bac correspondant.
L'écran affiche les informations importantes, notamment le poids en grammes et en livres, la catégorie de l'objet, la date et l'heure. Des voyants permettent également d'indiquer le fonctionnement normal du système ou la présence d'une erreur.
## Classification selon le poids
La plage de poids prévue pour les objets est de 5 g à 50 g.

Les objets seront classés en différentes catégories selon leur poids :
Objet léger : en bas de 30g.
Objet lourd : 30g à 50g.
Hors limite : supérieur à 50 g.

## Principaux composants
**Convoyeur**
Le convoyeur permet de transporter les objets entre les différentes étapes du système, de la détection jusqu'à la zone de tri.

**microcontrôleur**
L'Arduino est le contrôleur principal du système. Il reçoit les informations provenant des capteurs et commande les différents éléments, notamment le moteur du convoyeur, les bras mécaniques, les voyants et l'écran TFT.

**Capteur infrarouge**
Le capteur infrarouge permet de détecter la présence ou le passage d'un objet sur le convoyeur.

**Balance**
La balance permet de mesurer le poids de l'objet en grammes. Le système doit également permettre d'afficher le poids en livres sur l'écran tactile.

**Bras mécaniques**
Les bras mécaniques permettent de déplacer les objets vers le bac correspondant à leur catégorie de poids.

**Écran tactile**
L'écran tactile permet d'afficher les informations du système, notamment :
le poids en grammes ;
le poids en livres ;
le type de l'objet en français ;
le type de l'objet en anglais,espagnol et portugais ;
la date ;
l'heure.
Une lumière verte peut indiquer qu'un tri a été effectué correctement.
Une lumière rouge peut indiquer une erreur, par exemple lorsqu'un objet dépasse la limite de poids autorisée.

**Bouton**
Le bouton est prévu pour contrôler le système :
On bouton pour allumer le système ;
Off bouton pour éteindre le système.

## Détection des erreurs
Le système doit pouvoir détecter certaines situations anormales, notamment lorsqu'un objet reste bloqué sur le convoyeur.
Lorsqu'un blocage est détecté, une lumière clignotante avertit l'utilisateur.
Un objet dont le poids dépasse 50 g est également considéré comme un objet hors limite et peut être signalé comme une erreur.

## Modèle du convoyeur
Le prototype utilise un modèle de convoyeur imprimé en 3D.
Le modèle comprend notamment un moteur réducté, un capteur infrarouge réfléchissant et des micro-servos. 

[Model du convoyeur](https://cults3d.com/en/3d-model/various/conveyor-belts-simufab-3dtroop)





