# montage-projet.md

## 1. Vue d'ensemble des composants
Le système repose sur une structure mécanique modulaire couplée à un ensemble d'actionneurs et de capteurs pilotés électroniquement.

### Structure mécanique
* **Châssis principal** : Imprimé en 3D
* **Entraînement** : Rouleaux de convoyeur et courroie modulaire
* **Guidage et réception** : Rampes de chargement, butées et extensions optionnelles

### Électronique et Contrôle
* **Moteur à engrenages (DC)** : Entraînement de la bande transporteuse
* **Capteur infrarouge réfléchissant** : Détection du passage ou de la présence d'objets
* **Micro-servomoteur** : Actionneur pour le tri, l'éjection ou le blocage (barrière)
* **Arduino Nano Every** : Microcontrôleur central assurant la lecture des capteurs et le pilotage du moteur DC ainsi du servomoteur

---

## 2. Inventaire du matériel et visserie

| Type de composant | Spécifications / Modèle | Rôle / Utilisation |
| :--- | :--- | :--- |
| **Visserie M3.5** | M3.5 x 12 mm | Fixation des éléments de châssis principal |
| **Visserie M3** | M3 x 16 mm / M3 x 6 mm | Assemblage des supports et sous-ensembles |
| **Visserie M2** | M2 x 8 mm | Fixation des petits composants et capteurs |
| **Visserie M4** | M4 x 12 mm | Ancrage des structures à forte contrainte |
| **Microcontrôleur** | Arduino Nano Every | Unité de traitement logique et PWM |

---

## 3. Étapes d'assemblage mécanique

### Étape 1 : Assemblage du châssis
Assembler les différentes pièces imprimées en 3D à l'aide de la visserie répertoriée en suivant la séquence illustrée ci-dessous :

![Assemblage étapes 1 à 5](/images/etape1-2-3-4-5-montage-convoyeur.png)
![Assemblage étapes 6 à 8](/images/etape6-7-8-montage-convoyeur.png)
![Assemblage étapes 9 à 12](/images/etape9-10-11-12-montage-convoyeur.png)
![Assemblage étapes 13 à 16](/images/etape13-14-15-16-montage-convoyeur.png)
![Assemblage étapes 17 et 18](/images/etape17-18-montage-convoyeur.png)

### Étape 2 : Installation du moteur
* Fixer le moteur à engrenages sur son support dédié à l'extrémité du convoyeur.
* **Contrôles à effectuer** :
  * Vérifier le parfait alignement de l'axe.
  * S'assurer de la rotation fluide et sans friction du rouleau d'entraînement.
* **Mode de commande** : Variable par signal PWM (de 0 % à 100 %) pour l'ajustement de la vitesse.

### Étape 3 : Installation de la bande transporteuse
La longueur de la courroie dépend de la configuration de la ligne :

| Configuration du convoyeur | Nombre de maillons requis |
| :--- | :---: |
| **Module standard** | 38 maillons |
| **Extension de 8 cm** | + 18 maillons supplémentaires par section |

### Étape 4 : Installation du capteur infrarouge
* Positionner le capteur réfléchissant à proximité immédiate de la bande transporteuse.
* Ajuster la hauteur afin d'assurer une détection fiable de toutes les pièces en transit.

### Étape 5 : Installation du micro-servomoteur
* Fixer le micro-servo sur le support mécanique prévu.
* **Fonctions programmables** :
  * Barrière d'arrêt
  * Aiguillage / Trieur de pièces
  * Éjecteur latéral

### Étape 6 : Pre-assemblage et montage de la balance
* Effectuer le montage mécanique complet du module de pesée (cellule de charge) en amont.
* Installer et aligner l'ensemble sur la ligne du convoyeur..
