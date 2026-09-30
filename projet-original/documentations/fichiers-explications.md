# Explication du projet

## 1. Présentation du projet
Ce projet consiste à concevoir et réaliser un convoyeur automatisé capable de trier des objets selon leur poids. 

Le système transporte les pièces le long de la ligne, où un capteur infrarouge détecte leur présence avant qu'une balance n'effectue la mesure de masse. L'Arduino analyse ces données pour déterminer la catégorie de l'objet et commande un mécanisme de tri vers le bac approprié. Un écran tactile assure l'interface utilisateur en affichant l'état du système et les caractéristiques de l'objet en temps réel.

---

## 2. Fonctionnement général

1. **Transport et détection** : Mise en marche du convoyeur et détection de l'arrivée de l'objet par le capteur infrarouge.
2. **Mesure du poids** : Ancrage de l'objet sur la balance et acquisition de la masse en grammes par le microcontrôleur.
3. **Classification** : Comparaison de la valeur mesurée aux seuils prédéfinis pour déterminer la catégorie.
4. **Tri mécanique** : Activation des bras mécaniques pour diriger l'objet vers le bac correspondant.
5. **Affichage et signalisation** : Mise à jour de l'écran tactile (poids, catégorie, date/heure) et retour visuel via les voyants lumineux.

---

## 3. Classification selon le poids

La plage de mesure opérationnelle est comprise entre **5 g et 50 g**. La répartition s'effectue selon la grille suivante :

| Catégorie | Plage de poids | Action du système |
| :--- | :--- | :--- |
| **Objet léger** | Moins de $30\,\text{g}$ ($< 30\,\text{g}$) | Tri vers le bac 1 (Léger) |
| **Objet lourd** | De $30\,\text{g}$ à $50\,\text{g}$ | Tri vers le bac 2 (Lourd) |
| **Hors limite** | Supérieur à $50\,\text{g}$ ($> 50\,\text{g}$) | Signalement d'erreur et rejet/évacuation |

---

## 4. Inventaire des composants principaux

| Composant | Rôle / Description |
| :--- | :--- |
| **Convoyeur** | Structure imprimée en 3D assurant le transport des pièces de la zone de détection jusqu'à la zone de tri. |
| **Microcontrôleur (Arduino)** | Unité centrale traitant les entrées capteurs et contrôlant le moteur du convoyeur, les bras mécaniques, l'écran et les voyants. |
| **Capteur infrarouge** | Capteur réfléchissant positionné pour détecter la présence et le passage exact d'une pièce. |
| **Balance (Cellule de charge)** | Mesure de la masse en grammes, convertie également pour un affichage en livres ($\text{lb}$). |
| **Bras mécaniques** | Micro-servomoteurs permettant d'orienter ou d'éjecter la pièce vers son réceptacle dédié. |
| **Écran tactile TFT** | Interface visuelle affichant : masse ($\text{g}$ et $\text{lb}$), catégorie (traduite en français, anglais, espagnol et portugais), date et heure. |
| **Boutons de commande** | Interface physique d'allumage (**ON**) et d'arrêt (**OFF**) du système. |
| **Voyants lumineux** | Témoin vert (tri réussi) et témoin rouge (erreur ou dépacement de capacité). |

---

## 5. Détection des erreurs et sécurité

Le système intègre des routines de surveillance pour gérer les anomalies de fonctionnement :

| Type d'anomalie | Cause | Action corrective / Signalisation |
| :--- | :--- | :--- |
| **Blocage sur ligne** | Objet immobile ou coincé devant le capteur IR | Activation d'une lumière clignotante d'avertissement. |
| **Dépassement de masse** | Objet supérieur à $50\,\text{g}$ | Détection "Hors limite", affichage d'une alerte et voyant rouge. |

[Modèle du convoyeur](https://cults3d.com/en/3d-model/various/conveyor-belts-simufab-3dtroop)





