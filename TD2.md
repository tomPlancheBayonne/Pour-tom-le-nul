## TD2 Communtation Ethernet

### Exercice 1 (Introduction)

#### Soit le Hub Ethernet comprenant 8 ports à 100 Mb/s. Quel débit pratique maximum est-on en droit d'attendre pour un ordinateur connecté sur ce hub ?
*À cause des collisions perte de 40 à 60%*
Donc de 60 Mb/s à 40 Mb/s

#### Un Hub Ethernet peut-il comporter un mélange de ports à 10 Mb/s et à 100 Mb/s ?
Non, car il renvoi ce qu'il reçoit. Les ports sont tous indentiques.

#### Soit le commutateur Ethernet comprenant 12 ports à 100 Mb/s. Quel doit être le débit minimum thérorique de la carte de commutation pour ne pas être bloquant ?
Il faut que le débit minimum soit de 600 Mb/s. Car seulement 6 ports au maximum communiquent, les 12 ne peuvent pas communiquer en même temps.

#### Un commutateur Ethernet peut-il comporter un mélange de ports à 100 Mb/s et à 1 Gb/s ?

#### Quel est le nombre maximum théorique de trames par seconde qu'un Commutateur Ethernet peut recevoir sur un port à 1 Gb/s ?
Oui, longueur minimale de trame (64 bits) + silence intertrame (12 octets) + préambule (8 bits)
À diviser par le débit pour trouver le nombre de trames.

#### Soit une borne wifi 802.11g connectée à un port de commutateur à 100Mb/s. Soit 1à portables possédant une carte 802.11g connectés à la borne. Quel est le débit maximmum théorique peut espérer obtenir un utilisateur de portable ?

### Exercice 2
#### Soit le réseau Ethernet composé de dexu stations, A et B, d'adresses respectives @EtH_A et @ETH_B au niveau MAC et @IP_A et @IP_B au niveau IP. Décrivez, pas à pas, l'émission d'un datagramme IP de A vers B, sachant qu'aucune communication n'a eu lieu entre A et B.

###### A demande qui est IP_B
-   MAC_SRC : ETH_A
-   MAC_DEST : FF:FF:FF:FF:FF:FF
-   IP_SRC : IP_A
-   IP_DEST : IP_B

###### B envoie un ARP_reply à A
-   MAC_SRC : ETH_B
-   MAC_DEST : ETH_A
-   IP_SRC : IP_B
-   IP_DEST : IP_A

###### A envoie le datagramme à B
-   MAC_SRC : ETH_A
-   MAC_DEST : ETH_B
-   IP_SRC : IP_A
-   IP_DEST : IP_B

### Exercice 3

#### 1
Le poste A va demander une adresse IP via le protocole DHCP, c'est comme ça que le switch apprend l'existence de A.

#### 2
SW2 et SW3 recoivent un message de A, l'adresse MAC est donc inscrite dans leur table de commutation.

#### 3
<table>
<tr>
<th>Table de SW1</th>
<th>Table de SW2</th>
<th>Table de SW3</th>
</tr>
<tr>

<td>

| @MAC | port |
| :--: | :--: |
| ETH_A | 1 |
| ETH_B | 3 |
| ETH_X | 2 |
| ETH_Y | 2 |
| ETH_S1 | 2 |
| ETH_S2 | 2 |
| ETH_S3 | 2 |

</td><td>

| @MAC | port |
| :--: | :--: |
| ETH_A | 1 |
| ETH_B | 1 |
| ETH_X | 5 |
| ETH_Y | 5 |
| ETH_S1 | 2 |
| ETH_S2 | 3 |
| ETH_S3 | 4 |
</td><td>

| @MAC | port |
| :--: | :--: |
| ETH_A | 2 |
| ETH_B | 2 |
| ETH_X | 1 |
| ETH_Y | 3 |
| ETH_S1 | 2 |
| ETH_S2 | 2 |
| ETH_S3 | 2 |

</td></tr> </table>

#### 4
SW1 va oublier X et Y et SW3 va oublie A et B, mais SW2 étant relié aux deux groupe de travaux va les garder en mémoire.

#### 5
Bloquer au niveau du Switch.

#### 6
