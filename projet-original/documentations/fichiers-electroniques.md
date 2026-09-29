## 1.Schéma électrique


## 2. Alimentation et Tensions
Le circuit utilise deux rails d'alimentation distincts pour séparer la logique et la puissance :
* **+5V** : Alimentation logique reliée à la broche `VUSB` (broche 12) de l'Arduino Nano Every, au bouton-poussoir `SW1`, au capteur infrarouge (`JP7`), aux servomoteurs (`JP4`, `JP5`, `JP6`) et au module balance (`JP8`)[cite: 2].
* **+12V** : Rail de puissance relié directement au pôle positif (Pin 1) des trois moteurs DC (`JP1`, `JP2`, `JP3`)[cite: 2].
* **GND** : Masse commune du circuit reliée aux broches 14 et 19 de l'Arduino Nano Every, aux cathodes des LEDs, aux résistances de tirage, aux émetteurs des transistors T1/T2/T3, et aux connecteurs périphériques[cite: 2].

---

## 3. Table de brochage (Pinout)

| Broche Arduino | Signal / Pin CI | Composant / Periphérique relié | Valeur / Type | Description / Rôle |
| :--- | :--- | :--- | :--- | :--- |
| **A0 / D14** | Pin 4 | LED1 ➔ R1 | $330\,\Omega$ | Commande LED 1[cite: 2] |
| **A1 / D15** | Pin 5 | LED2 ➔ R2 | $330\,\Omega$ | Commande LED 2[cite: 2] |
| **A2 / D16** | Pin 6 | LED3 ➔ R3 | $330\,\Omega$ | Commande LED 3[cite: 2] |
| **A3 / D17** | Pin 7 | SW1 / R4 | $1000\,\Omega$ ($1\,\text{k}\Omega$) | Entrée bouton-poussoir avec résistance Pull-Down[cite: 2] |
| **D2** | Pin 20 | JP7 (Pin 1) | Capteur Infrarouge | Signal de lecture IR[cite: 2] |
| **D3** | Pin 21 | Transistor T1 (Base) via R5 | $1000\,\Omega$ | Commande Moteur DC 1 (JP1)[cite: 2] |
| **D4** | Pin 22 | Transistor T2 (Base) via R6 | $1000\,\Omega$ | Commande Moteur DC 2 (JP2)[cite: 2] |
| **D5** | Pin 23 | Transistor T3 (Base) via R7 | $1000\,\Omega$ | Commande Moteur DC 3 (JP3)[cite: 2] |
| **D6** | Pin 24 | JP4 (Pin 1) | Servomoteur 1 | Signal de commande PWM Servo 1[cite: 2] |
| **D9** | Pin 27 | JP5 (Pin 1) | Servomoteur 2 | Signal de commande PWM Servo 2[cite: 2] |
| **D10** | Pin 28 | JP6 (Pin 1) | Servomoteur 3 | Signal de commande PWM Servo 3[cite: 2] |
| **D11** | Pin 29 | JP8 (Pin 1) | Balance | Canal de communication 1 (ex. SCK/DT)[cite: 2] |
| **D12** | Pin 30 | JP8 (Pin 2) | Balance | Canal de communication 2 (ex. DT/SCK)[cite: 2] |

---

## 4. Détail des schémas de câblage et branchements

### LEDs d'indication
* **LED1** : Anode sur broche `A0/D14` via résistance `R1` ($330\,\Omega$), Cathode à la masse (`GND`)[cite: 2].
* **LED2** : Anode sur broche `A1/D15` via résistance `R2` ($330\,\Omega$), Cathode à la masse (`GND`)[cite: 2].
* **LED3** : Anode sur broche `A2/D16` via résistance `R3` ($330\,\Omega$), Cathode à la masse (`GND`)[cite: 2].

### Bouton-Poussoir (Entrée Utilisateur)
* **SW1** : Branché entre `+5V` et la broche `A3/D17`[cite: 2].
* **R4 ($1000\,\Omega$)** : Placé en résistance de rappel à la masse (Pull-Down) entre la broche `A3/D17` et `GND` pour garantir un état bas (0V) au repos[cite: 2].

### Capteur Infrarouge (`JP7`)
* **Pin 1** : Signal relié à la broche `D2` de l'Arduino[cite: 2].
* **Pin 2** : Alimentation `+5V`[cite: 2].
* **Pin 3** : Masse `GND`[cite: 2].

### Commande Moteurs DC (`JP1`, `JP2`, `JP3`)
Chaque moteur DC est commuté au zéro via un transistor NPN (T1, T2, T3) en configuration Low-Side :
* **Moteur DC 1 (`JP1`)** :
  * `JP1` Pin 1 ➔ `+12V`[cite: 2]
  * `JP1` Pin 2 ➔ Collecteur du transistor `T1`[cite: 2]
  * Base de `T1` ➔ Reliée à la broche `D3` via la résistance `R5` ($1000\,\Omega$)[cite: 2]
  * Émetteur de `T1` ➔ Masse `GND`[cite: 2]
* **Moteur DC 2 (`JP2`)** :
  * `JP2` Pin 1 ➔ `+12V`[cite: 2]
  * `JP2` Pin 2 ➔ Collecteur du transistor `T2`[cite: 2]
  * Base de `T2` ➔ Reliée à la broche `D4` via la résistance `R6` ($1000\,\Omega$)[cite: 2]
  * Émetteur de `T2` ➔ Masse `GND`[cite: 2]
* **Moteur DC 3 (`JP3`)** :
  * `JP3` Pin 1 ➔ `+12V`[cite: 2]
  * `JP3` Pin 2 ➔ Collecteur du transistor `T3`[cite: 2]
  * Base de `T3` ➔ Reliée à la broche `D5` via la résistance `R7` ($1000\,\Omega$)[cite: 2]
  * Émetteur de `T3` ➔ Masse `GND`[cite: 2]

### Moteurs Servomoteurs (`JP4`, `JP5`, `JP6`)
* **Moteur Servo 1 (`JP4`)** : Pin 1 ➔ `D6` (PWM) | Pin 2 ➔ `+5V` | Pin 3 ➔ `GND`[cite: 2]
* **Moteur Servo 2 (`JP5`)** : Pin 1 ➔ `D9` (PWM) | Pin 2 ➔ `+5V` | Pin 3 ➔ `GND`[cite: 2]
* **Moteur Servo 3 (`JP6`)** : Pin 1 ➔ `D10` (PWM) | Pin 2 ➔ `+5V` | Pin 3 ➔ `GND`[cite: 2]

### Balance (`JP8`)
* **Pin 1** ➔ Broche `D11` de l'Arduino[cite: 2]
* **Pin 2** ➔ Broche `D12` de l'Arduino[cite: 2]
* **Pin 3** ➔ Alimentation `+5V`[cite: 2]
* **Pin 4** ➔ Masse `GND`[cite: 2]
