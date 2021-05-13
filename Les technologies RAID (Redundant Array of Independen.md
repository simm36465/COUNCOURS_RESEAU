- [Les technologies RAID (Redundant Array of Independent Disks)](#les-technologies-raid--redundant-array-of-independent-disks-)
- [Les types RAID](#les-types-raid)
  * [RAID 0 (Volume agrégé par bandes , Striping)](#raid-0--volume-agr-g--par-bandes---striping-)
  * [RAID 1 (Disques en miroir, Mirroring)](#raid-1--disques-en-miroir--mirroring-)
  * [RAID 2 (volume agrégé par bandes à parité, Striping with parity)](#raid-2--volume-agr-g--par-bandes---parit---striping-with-parity-)
  * [RAID 3 (Bit parity)](#raid-3--bit-parity-)
  * [RAID 4 (Block parity)](#raid-4--block-parity-)
  * [RAID 5 (Parité répartie)](#raid-5--parit--r-partie-)
  * [RAID 6](#raid-6)
  * [RAID 7](#raid-7)
  * [RAID combinés](#raid-combin-s)
  * [Comparaison](#comparaison)
  * [RAID en pratique](#raid-en-pratique)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>



### Les technologies RAID (Redundant Array of Independent Disks)
c'est un technologies qui permettent d'utiliser plusieurs disques durs pour gagner performances, espace disque, fiabilité.

### Les types RAID
#### RAID 0 (Volume agrégé par bandes , Striping)
les données sont réparties sur l'ensemble des disques durs.
* au moins 2 disques durs (même capacité)
* aucune redondance (aucune sécurité des données)
* traitement rapide d'une grande quantité de données
#### RAID 1 (Disques en miroir, Mirroring)
la duplication des données stocker sur l'esnsemble des disques utilisés.
* au moins 2 disques durs
* excellent niveau de protection des données
* Les coûts de stockage sont élevés
#### RAID 2 (volume agrégé par bandes à parité, Striping with parity)
Il combine la méthode du RAID 0 avec un code de contrôle d'erreur par code de Hamming (code ECC)
* au moins 4 disques durs
* bon niveau de sécurité
* mauvaises performances
#### RAID 3 (Bit parity)
les données sont réparties sous forme *d'octets* sur chaque disque et de dédier un des disques au stockage d'un bit de parité.
* au moins 3 disques durs
* bon performances et redondances
* Si on perd le disque de parité, on perd le RAID entier
#### RAID 4 (Block parity)
les données sont réparties sous forme de *blocs* sur chaque disque et de dédier un des disques au stockage d'un bit de parité.
* au moins 3 disques durs
* bon performances et redondances
* Si on perd le disque de parité, on perd le RAID entier
#### RAID 5 (Parité répartie)
les données et les bits de parité sont réparties sur l'ensemble des disques durs
* au moins 3 disques durs
* Excellente tolérance aux pannes
* Hot-plug possible
* Excellente performances
> Le RAID 5 est la solution la plus répandue dans les entreprises
#### RAID 6
Le mode RAID 6 est similaire au mode 5 mais utilise plusieurs disques de parité (2 disques)
* au moins 4 disques durs
* assurer la redondance

#### RAID 7
les informations à stocker sont réparties sur plusieurs disques de données avec un ou plusieurs disques de parité.
* au moins 4 disques durs
* Excellente performances 
* peuvent administrés sur une liaison Ethernet à travers un agent SNMP
#### RAID combinés
l'utilisation d'un concept de RAID classique sur des éléments constitutifs qui sont eux-mêmes le résultat d'un concept RAID classique
* RAID 01 (raid 0 + raid 1) : au moins 4 disques durs
* RAID 10 (raid 1 + raid 0) : au moins 4 disques durs
* RAID 15 (raid 1 + raid 5) : au moins 6 disques durs
* RAID 50 (raid 5 + raid 0) : au moins 6 disques durs
* RAID 51 (raid 5 + raid 1) : au moins 6 disques durs
#### Comparaison

1. **la sécurité :**RAID 1 et 5 offrent tous les deux un niveau de sécurité élevé
2. **Les performances :**RAID 1 offre de meilleures performances que RAID 5

#### RAID en pratique

1. **façon logicielle** : il s'agit généralement d'un driver au niveau du système d'exploitation de l'ordinateur capable de créer un seul volume logique avec plusieurs disques (SCSI ou IDE).
2. **façon matérielle**
    - DASD (Direct Access Stockage Device) : il s'agit d'unités de stockage externes pourvues d'une alimentation propre. De plus ces matériels sont dotés de connecteurs permettant l'échange de disques à chaud (on dit généralement que ce type de disque est hot swappable). Ce matériel gère lui-même ses disques, si bien qu'il est reconnu comme un disque SCSI standard.
    - contrôleurs de disques RAID : il s'agit de cartes s'enfichant dans des slots PCI ou ISA et permettant de contrôler plusieurs disques durs.
