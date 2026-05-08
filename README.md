# Projet ESP32 – Conception Électronique 2K26

## Contexte

Dans le cadre du projet de conception électronique, vous devez réaliser une carte de développement basée sur un **ESP32-PICO-D4**.

Le projet s’appuie sur un cahier des charges client fictif : **Ventec Systems**, entreprise spécialisée dans les AGV industriels. La carte doit permettre le monitoring d’un robot alimenté par une batterie 36V, avec mesure de courant, surveillance thermique, communication BLE et reprogrammation terrain.

Le cahier des charges complet ainsi que l’énoncé du projet sont disponibles dans le dossier :
```text
10_doc_ext/
```
Le projet Altium est situé dans :
```text
30_src/
```
Fichier projet principal :
```text
ESP32_Projet.PrjPcb
```

## Objectif du projet

Chaque équipe doit réaliser :

une analyse fonctionnelle du système ;
la sélection et l’étude des composants ;
la schématique de la carte ;
le routage PCB ;
les fichiers de fabrication ;
un rapport expliquant les choix techniques.

La carte doit respecter une taille maximale de :
```text
70 mm x 50 mm
```
Tous les composants doivent être placés uniquement sur la face TOP du PCB.

## Organisation des équipes

Le projet est réalisé en 5 équipes.

Chaque équipe doit travailler sur sa propre branche Git.

Format obligatoire du nom de branche :
```text
Equipe_1
Equipe_2
Equipe_3
Equipe_4
Equipe_5
```

## Structure du dépôt
```text
/10_doc_ext/
    CDC-VENTEC_SYSTEMS.pdf
    Enonce-Projet2k26_ESP32.pdf

/30_src/
    Projet Altium
    Librairies SCH_Lib / PCB_Lib
    PCB vierge
    Schématique vide
```

## Projet Altium

### Composants principaux

Les composants principaux imposés sont :

Microcontrôleur : ESP32-PICO-D4
Driver USB-UART : CP2104-F03-GM
Connecteur USB-C : USB4085-GF-A
Capteur de courant : INA237AIDGST

Des résistances, condensateurs, LEDs, connecteurs Grove / MikroBus, antenne, boutons reset / boot et autres composants seront également nécessaires.

### Contraintes principales

#### Alimentation

La carte doit pouvoir être alimentée par trois sources :

USB-C : 5V
BT : 3.7V à 10V
HT : jusqu’à 36V

La priorité d’alimentation doit être :
```text
USB > BT > HT
```
La gestion de priorité doit être réalisée matériellement, sans dépendre du firmware.

#### Mesures

La carte doit permettre :
- la mesure du courant sur la batterie 36V
- la surveillance de températures PCB
- la mesure de température ambiante
- l’ajout de capteurs via Grove / MikroBus

#### Communication

La carte doit intégrer :
- communication BLE
- USB-C pour reprogrammation et extraction des logs
- protection des lignes USB
- gestion de l’antenne BLE avec adaptation du plan de masse

#### IHM

La carte doit intégrer :
- LED verte de fonctionnement normal
- LED rouge d’alarme
- buzzer piloté par l’ESP32
- boutons reset et boot accessibles

## Règles de conception imposées
### Schématique

- Schématique en mils
- Titre, révision et nom du dessinateur attendus
- Paires différentielles clairement indiquées

### PCB

- PCB en mm
- Taille maximale : 70 mm x 50 mm
- Aucun composant sur la face Bottom
- Pas d’angles droits sur les pistes
- Arrivée des pistes au centre des pads
- Plan de masse obligatoire
- Plan d’alimentation recommandé
- Vias : pastille 0.85 mm, perçage 0.35 mm
- Sérigraphie : largeur 0.15 mm
- Impédance 90 Ω sur la ligne de reprogrammation UART
- Impédance 50 Ω sur la ligne RF
- Adaptation du plan de masse autour de l’antenne BLE

## Barème : Update en cours

## Workflow Git
1. Cloner le dépôt
```bash
git clone https://github.com/COURS-YNOV/STUDENT_ESP32_2K26.git
cd STUDENT_ESP32_2K26
```
2. Créer la branche de votre équipe
```bash
git checkout -b Equipe_X
```
Exemple : 
```bash
git checkout -b Equipe_1
```

3. Travailler uniquement sur votre branche

Ne travaillez jamais directement sur main.

4. Ajouter vos fichiers
```bash
git add .
```

5. Faire un commit
```bash
git commit -m "avancement projet ESP32"
```

6. Push les modifications sur votre branch
```bash
git push Equipe_X
```
## Rapport attendu

Le rapport doit contenir :
- Les analyses fonctionnelles (AF 1 & AF 2)
- L’explication des différents blocs schématiques
- Les choix techniques réalisés
- Deux problèmes rencontrés pendant le projet ainsi que leurs solutions
- Les captures ou éléments utiles à la compréhension du projet

Le rapport doit être rendu au format PDF.

## Conseils
- Lire entièrement le cahier des charges avant de commencer
- Répartir les tâches dans l’équipe
- Vérifier régulièrement le DRC
- Commiter souvent
- Générer les Gerbers même si le projet n’est pas terminé
- Utiliser la documentation et les tutoriels vus en cours

# Bon courage à tous !