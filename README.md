# RP2040_First_Board

## Objectif

Je me lance dans la réalisation et l’assemblage d’une PCB, avec comme cœur de projet le microcontrôleur **RP2040**. L’idée, c’est de me faire la main sur la conception de circuits électroniques basiques (microcontrôleur + périphériques + alimentation), sur le design de PCB, et sur la programmation dans un nouvel environnement. J’utilise ce GitHub comme support de projet, pour y définir les specs techniques, et poser une base de travail claire. C’est un projet perso, rien de formel, donc je ne vais pas trop me prendre la tête sur la forme : je me concentre surtout sur le fond. Je pars avec très peu de bagage en électronique et juste quelques petites expériences. Je compte me former en ligne, en m’aidant de forums, tutos YouTube, ChatBot, et en m’inspirant de projets existants.

## Charges du projet

Je vais utiliser uniquement des composants que j’ai déjà en stock (récup’), ce qui m’évite de passer du temps à chercher des références ou passer commande. C’est pas forcément le meilleur choix de composants, mais c’est ce que j’ai, donc je m’en contente.

### Microcontrôleur

J’ai choisi un **RP2040**, un microcontrôleur dual-core ARM Cortex-M0+ cadencé à 133 MHz, avec 264 Ko de RAM et un contrôleur USB 1.1 intégré. Il offre 30 broches GPIO polyvalentes avec support ADC, PWM, I²C, SPI et UART. Il peut être programmé en MicroPython ou avec le Pico C SDK. Pour ce projet, je vais utiliser le Pico SDK : coder en C me permettra de gérer le dual-core librement, ce qui n’est pas possible avec MicroPython (et j’ai envie de tester ça).

### Flash

Je vais utiliser une **25Q64JVSIQ**, une mémoire flash SPI NOR de 64 Mbit (8 Mo), avec des vitesses de lecture jusqu’à 104 MHz. Le RP2040 n’ayant pas de flash interne, j’en ai besoin pour stocker le firmware et les données de manière non volatile.

### Écran

J’ai un petit écran OLED basé sur le **SSD1306**, contrôleur compatible I²C/SPI, en 128x64 pixels monochrome. C’est compact, peu gourmand, et ça permet d’avoir une interface visuelle simple pour le projet.

### Contrôleur de charge

J’utilise un **TP4056E**, un chargeur linéaire pour batterie Li-Ion (une seule cellule). Il intègre les protections de base (surcharge, décharge, court-circuit), et se charge via USB. C’est parfait pour alimenter simplement un montage à base de RP2040.

### IC de mesure

J’ai aussi un **INA3221**, un moniteur de tension/courant trois canaux (jusqu’à 26 V), avec interface I²C. Il me servira à suivre la conso des différents rails du circuit, détecter des surcharges, etc.

### Connectique

Je vais intégrer un **port USB-C femelle 16 pins**, compatible USB 2.0. Il est compact, réversible, et permet de gérer à la fois l’alim 5 V et la communication USB, que ce soit pour charger via le **TP4056E** ou programmer le **RP2040**.

### Autre

Je compte ajouter deux ou trois **LEDs** pour débug rapidement des états du **RP2040** (même si j’ai déjà le **SSD1306**, je trouve ça pratique et ça me permet de jouer un peu avec les GPIO). Je vais aussi prévoir quelques **boutons** pour interagir avec le projet, comme naviguer entre différentes fonctionnalités.
