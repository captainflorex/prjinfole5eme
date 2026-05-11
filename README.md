# Super Bulles - Projet INFO S2

Jeu 2D en C avec Allegro 4, inspire de Pang.
Le joueur se deplace horizontalement, tire sur des bulles qui se divisent, et doit finir les niveaux avant la fin du temps.

## Langues / Languages

- [Français](#super-bulles---projet-info-s2)
- [English](#english-translation)
- [Español](#traducción-al-español)
- [Deutsch](#deutsche-übersetzung)

## Description

Super Bulles est un jeu d'arcade solo dans lequel chaque niveau augmente la difficulte (vitesse, nombre et taille des bulles).
Le but est de survivre, gerer le temps imparti et maximiser le score en eliminant toutes les bulles.

## Presentation

- Langage: C99
- Bibliotheque graphique: Allegro 4 (`allegro.h`)
- Resolution: 800x600
- Moteur de jeu: boucle a 60 FPS avec timer Allegro
- Etats de l'application:
  - menu principal
  - saisie pseudo
  - en jeu
  - pause
  - victoire / defaite

## Fonctionnalites

- Menu principal:
  - Nouvelle partie
  - Reprendre une partie
  - Regles du jeu
  - Quitter
- 4 niveaux de difficulte croissante
- Systeme de bulles qui se divisent en tailles plus petites
- HUD: pseudo, score, niveau, temps restant
- Ecran de pause et decompte de debut de niveau
- Sauvegarde/chargement simple par pseudo dans [sauvegardes.txt](sauvegardes.txt)

## Controles

- Fleche gauche / droite: deplacement
- Espace: tirer
- P: pause / reprise
- Echap:
  - quitter la partie en cours vers le menu
  - revenir depuis l'ecran des regles
- Entree:
  - valider un choix dans le menu
  - valider le pseudo
  - revenir au menu apres victoire/defaite

## Arborescence utile

- [src/](src/): fichiers source C
- [header/](header/): headers
- [ressources/](ressources/): assets (fond et sprites)
- [html/](html/) et [latex/](latex/): documentation generee (Doxygen)
- [cmake-build-debug/](cmake-build-debug/): artefacts de build CMake

## Prerequis

Sur Windows (MinGW recommande):

- GCC
- CMake (optionnel)
- Allegro 4 developpement (bibliotheques + headers)

Exemple de bibliotheques a l'edition de liens:

- `-lmingw32`
- `-lalleg44`

## Compilation rapide (GCC)

Depuis la racine du projet (`Projet_INFO_SEM2`):

```bash
gcc -Wall -Wextra -g3 \
  src/main.c src/affichage.c src/jeu.c src/entrees.c src/menu.c src/sauvegarde.c \
  -Iheat -o SuperBulles.exe -lmingw32 -lalleg44
```

Execution:

```bash
./SuperBulles.exe
```

## Compilation avec CMake

Le projet contient un [CMakeLists.txt](CMakeLists.txt).
Si votre environnement Allegro 4 est correctement configure:

```bash
cmake -S . -B build
cmake --build build
```

Puis lancez l'executable genere dans le dossier `build/`.

## Sauvegardes

- Fichier utilise: [sauvegardes.txt](sauvegardes.txt) (a la racine d'execution)
- Format d'une ligne: `pseudo niveau`
- Le chargement reprend le dernier niveau trouve pour un pseudo

## Ressources et remarques

- Le fond principal est present dans [ressources/fonds/fond_jeu.bmp](ressources/fonds/fond_jeu.bmp).
- Plusieurs sprites attendus dans [ressources/sprites/](ressources/sprites/) peuvent etre absents.
  - Le code gere des fallback graphiques (formes colorees) si un sprite manque.
- Une partie du chargement de fond dans [src/affichage.c](src/affichage.c) utilise un chemin absolu local.
  - Si le fichier n'est pas trouve, un fond de secours est cree automatiquement.

## Documentation

- Config Doxygen: [Doxyfile](Doxyfile)
- Sorties deja presentes: [html/](html/) et [latex/](latex/)
- Documentation complete (PDF): [refman.pdf](latex/refman.pdf)

## English translation

### Super Bulles - INFO S2 Project

2D C game with Allegro 4, inspired by Pang.
The player moves horizontally, shoots bubbles that split, and must complete levels before time runs out.

### Description

Super Bulles is a single-player arcade game where each level increases the difficulty (bubble speed, count, and size).
The objective is to survive, manage the time limit, and maximize score by clearing all bubbles.

### Overview

- Language: C99
- Graphics library: Allegro 4 (`allegro.h`)
- Resolution: 800x600
- Game loop: 60 FPS with Allegro timer
- Application states:
  - main menu
  - nickname input
  - in game
  - pause
  - win / lose

### Features

- Main menu:
  - New game
  - Continue game
  - Game rules
  - Quit
- 4 increasing difficulty levels
- Bubble splitting system (large bubbles split into smaller ones)
- HUD: nickname, score, level, remaining time
- Pause screen and level-start countdown
- Simple save/load by nickname in [sauvegardes.txt](sauvegardes.txt)

### Controls

- Left / Right arrow: move
- Space: shoot
- P: pause / resume
- Escape:
  - quit current game to menu
  - return from rules screen
- Enter:
  - confirm menu selection
  - confirm nickname
  - return to menu after win/lose

### Documentation

- Doxygen config: [Doxyfile](Doxyfile)
- Generated outputs: [html/](html/) and [latex/](latex/)
- Full documentation PDF: [refman.pdf](latex/refman.pdf)

## Traducción al español

### Super Bulles - Proyecto INFO S2

Juego 2D en C con Allegro 4, inspirado en Pang.
El jugador se mueve horizontalmente, dispara burbujas que se dividen y debe terminar los niveles antes de que se acabe el tiempo.

### Descripción breve

- Lenguaje: C99
- Biblioteca grafica: Allegro 4 (`allegro.h`)
- Resolucion: 800x600
- Modos principales: menu, juego, pausa, victoria/derrota
- Guardado/carga por apodo en el archivo de guardado [sauvegardes.txt](sauvegardes.txt)

## Deutsche Übersetzung

### Super Bulles - INFO S2 Projekt

2D-Spiel in C mit Allegro 4, inspiriert von Pang.
Der Spieler bewegt sich horizontal, schießt auf Blasen, die sich teilen, und muss die Level vor Ablauf der Zeit abschließen.

### Kurzbeschreibung

- Sprache: C99
- Grafikbibliothek: Allegro 4 (`allegro.h`)
- Auflösung: 800x600
- Hauptzustände: Menu, Spiel, Pause, Sieg/Niederlage
- Speichern/Laden per Spielername in der Speicherdatei [sauvegardes.txt](sauvegardes.txt)

## Auteurs

Floriant CHAFFRAY
Tom PETITJEAN
Remi MATTEODA
Candice OSWALD
