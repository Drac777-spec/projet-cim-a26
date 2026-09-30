# Partie électronique du projet

## Schéma électrique

![Texte alternatif](/images/schema-electrique.png)

## Alimentation et Tensions
Le circuit utilise deux rails d'alimentation distincts pour séparer la logique et la puissance :
* **+5V** : Alimentation logique reliée à la broche VUSB (broche 12) de l'Arduino Nano Every, au bouton-poussoir SW1, au capteur infrarouge (JP7), aux servomoteurs (JP4, JP5, JP6) et au module balance (JP8).
* **+12V** : Rail de puissance relié directement au pôle positif (Pin 1) des trois moteurs DC (JP1, JP2, JP3).
* **GND** : Masse commune du circuit reliée aux broches 14 et 19 de l'Arduino Nano Every, aux cathodes des LEDs, aux résistances de tirage, aux émetteurs des transistors T1/T2/T3, et aux connecteurs périphériques.

## Table de brochage (Pinout)

| Broche Arduino | Signal / Pin CI | Composant / Periphérique relié | Valeur / Type | Description / Rôle |
| :--- | :--- | :--- | :--- | :--- |
| **A0 / D14** | Pin 4 | LED1 ➔ R1 | $330\,\Omega$ | Commande LED 1 |
| **A1 / D15** | Pin 5 | LED2 ➔ R2 | $330\,\Omega$ | Commande LED 2 |
| **A2 / D16** | Pin 6 | LED3 ➔ R3 | $330\,\Omega$ | Commande LED 3 |
| **A3 / D17** | Pin 7 | SW1 / R4 | $1000\,\Omega$ ($1\,\text{k}\Omega$) | Entrée bouton-poussoir avec résistance Pull-Down |
| **D2** | Pin 20 | JP7 (Pin 1) | Capteur Infrarouge | Signal de lecture IR |
| **D3** | Pin 21 | Transistor T1 (Base) via R5 | $1000\,\Omega$ | Commande Moteur DC 1 (JP1) |
| **D4** | Pin 22 | Transistor T2 (Base) via R6 | $1000\,\Omega$ | Commande Moteur DC 2 (JP2) |
| **D5** | Pin 23 | Transistor T3 (Base) via R7 | $1000\,\Omega$ | Commande Moteur DC 3 (JP3) |
| **D6** | Pin 24 | JP4 (Pin 1) | Servomoteur 1 | Signal de commande PWM Servo 1 |
| **D9** | Pin 27 | JP5 (Pin 1) | Servomoteur 2 | Signal de commande PWM Servo 2 |
| **D10** | Pin 28 | JP6 (Pin 1) | Servomoteur 3 | Signal de commande PWM Servo 3 |
| **D11** | Pin 29 | JP8 (Pin 1) | Balance | Canal de communication 1 (ex. SCK/DT) |
| **D12** | Pin 30 | JP8 (Pin 2) | Balance | Canal de communication 2 (ex. DT/SCK) |

## Détail des schémas de câblage et branchements

### LEDs d'indication
* **LED1** : Anode sur broche A0/D14 via résistance R1 ($330\,\Omega$), Cathode à la masse (GND).
* **LED2** : Anode sur broche A1/D15 via résistance R2 ($330\,\Omega$), Cathode à la masse (GND).
* **LED3** : Anode sur broche A2/D16 via résistance R3 ($330\,\Omega$), Cathode à la masse (GND).

### Bouton-Poussoir (Entrée Utilisateur)
* **SW1** : Branché entre +5V et la broche A3/D17.
* **R4 ($1000\,\Omega$)** : Placé en résistance de rappel à la masse (Pull-Down) entre la broche A3/D17 et GND pour garantir un état bas (0V) au repos.

### Capteur Infrarouge (JP7)
* **Pin 1** : Signal relié à la broche D2 de l'Arduino.
* **Pin 2** : Alimentation +5V.
* **Pin 3** : Masse GND.

### Commande Moteurs DC (JP1, JP2, JP3)
Chaque moteur DC est commuté au zéro via un transistor NPN (T1, T2, T3) en configuration Low-Side :
* **Moteur DC 1 (JP1)** :
  * JP1 Pin 1 ➔ +12V
  * JP1 Pin 2 ➔ Collecteur du transistor T1
  * Base de T1 ➔ Reliée à la broche D3 via la résistance R5 ($1000\,\Omega$)
  * Émetteur de T1 ➔ Masse GND
* **Moteur DC 2 (JP2)** :
  * JP2 Pin 1 ➔ +12V
  * JP2 Pin 2 ➔ Collecteur du transistor T2
  * Base de T2 ➔ Reliée à la broche D4 via la résistance R6 ($1000\,\Omega$)
  * Émetteur de T2 ➔ Masse GND
* **Moteur DC 3 (JP3)** :
  * JP3 Pin 1 ➔ +12V
  * JP3 Pin 2 ➔ Collecteur du transistor T3
  * Base de T3 ➔ Reliée à la broche D5 via la résistance R7 ($1000\,\Omega$)
  * Émetteur de T3 ➔ Masse GND

### Moteurs Servomoteurs (JP4, JP5, JP6)
* **Moteur Servo 1 (JP4)** : Pin 1 ➔ D6 (PWM) | Pin 2 ➔ +5V | Pin 3 ➔ GND
* **Moteur Servo 2 (JP5)** : Pin 1 ➔ D9 (PWM) | Pin 2 ➔ +5V | Pin 3 ➔ GND
* **Moteur Servo 3 (JP6)** : Pin 1 ➔ D10 (PWM) | Pin 2 ➔ +5V | Pin 3 ➔ GND

### Balance (JP8)
* **Pin 1** ➔ Broche D11 de l'Arduino
* **Pin 2** ➔ Broche D12 de l'Arduino
* **Pin 3** ➔ Alimentation +5V
* **Pin 4** ➔ Masse GND
