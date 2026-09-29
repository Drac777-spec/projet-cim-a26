# Convoyeur Simufab 3DTROOP

## Composants principaux

Le système est composé des éléments suivants :

### Structure mécanique

- Châssis principal imprimé en 3D
- Rouleaux de convoyeur
- Courroie modulaire
- Rampes de chargement
- Butées 
- Extensions optionnelles

### Électronique

#### Moteur à engrenages

Responsable de l'entraînement de la bande transporteuse. 

#### Capteur infrarouge réfléchissant

Permet de détecter le passage ou la présence d'un objet sur le convoyeur. 

#### Micro-servo

Peut être utilisé comme trieur ou barrière pour dévier des pièces. 

#### Arduino Nano Every

Microcontrôleur chargé de :

- Lire les capteurs
- Contrôler le moteur
- Commander le servo

## Montage mécanique

### Étape 1 : Assemblage du châssis

Assembler les différentes pièces imprimées 3D selon les illustrations du guide Simufab.

Vis utilisées :

- M3.5x12
- M3x16
- M3x6
- M2x8
- M4x12

### Étape 2 : Installation du moteur

Fixer le moteur à engrenages sur son support à l'extrémité du convoyeur. 
Utilisation du PWM de 0 à 100% pour régler la vitesse.

Vérifier :

- L'alignement de l'axe
- La rotation libre du rouleau

### Étape 3 : Installation de la bande transporteuse

Pour un module standard :

- 38 maillons de convoyeur

Pour chaque extension de 8 cm :

- Ajouter 18 maillons supplémentaires

### Étape 4 : Installation du capteur infrarouge

Monter le capteur près de la bande afin qu'il puisse détecter les objets transportés. 

### Étape 5 : Installation du servo

Fixer le micro-servo sur le support prévu.
Utiliser la librairie du servo pour programmer.

Fonction possible :
- Barrière
- Trieur
- Éjecteur

### Étape 6 : Installation de la balance

Monter la balance en amont avant de l'installer sur le convoyeur.
