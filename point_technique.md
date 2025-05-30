![logo](https://github.com/user-attachments/assets/ef167c65-dfe7-4fe2-8ad3-174e812d3178)  
## 1. Contexte et objectifs

Ce projet implémente le jeu 3D en JavaScript (Babylon.js) avec :  
- un menu principal, un sélecteur de niveaux et un écran de chargement  
- une gestion de la scène (terrain, environnement, particules, tempête)  
- un système de joueurs, ennemis et alliés avec IA basique  
- un système de balle, des effets visuels et un HUD (FPS, boussole)  
- un gestionnaire de niveaux pour organiser progression et transitions  

L’objectif est de proposer une architecture modulaire et extensible, avec un cœur (`app.js`) orchestrant l’initialisation, le chargement et la boucle de jeu.

## 2. Technologies et dépendances

- **Babylon.js** (`@babylonjs/core`, loaders, inspector, debugLayer) pour le rendu 3D  
- **ES modules** (import/export)  
- **LocalStorage** pour persister la progression (clé `gameStarted`)  
- **CSS** (src/style.css) pour le canvas et l’UI basique  

Aucune autre librairie externe n’est utilisée : tout le code métier (IA, gestion de scène, UI) est propriétaire.

## 3. Architecture générale
``` plaintext
app.js
 ├─ camera/            ← gestion de la caméra (setupCamera, cameraManager.js)
 ├─ scene/             ← gestion de la scène (environment.js, mapGestion.js)
 ├─ joueur/            ← entités joueur (player.js, animations.js)
 ├─ ennemis/           ← IA ennemie (EnnemiAI.js)
 ├─ amis/              ← IA alliée (AmiAI.js)
 ├─ armes/             ← projectiles et munitions (balles.js)
 ├─ evenements/        ← contrôles utilisateur (controls.js)
 ├─ effects/           ← effets visuels (visualEffects.js)
 ├─ storm/             ← tempête dynamique (PurpleStorm.js)
 ├─ ui/                ← écrans et HUD (mainMenu.js, loadingScreen.js, fpsDisplay.js, etc.)
 ├─ levels/            ← gestionnaire de niveaux (levelManager.js, LevelX.js)
 ├─ config/            ← paramètres de jeu (gameConfig.js)
 └─ utils/             ← utilitaires (imageSlice.js, divers helpers)
```

- **app.js** est le point d’entrée :  
  - initialise Babylon.js (`Engine`, canvas)  
  - choisit menu ou chargement selon `localStorage`  
  - appelle `startGame()` pour lancer la boucle  
- **LevelManager** orchestre le chargement/transition entre niveaux  
- **mapGestion** découpe et charge dynamiquement les parties de la carte  
- **gameConfig** centralise tous les paramètres (vitesse, tailles, distances, IA)


## 4. Modélisation 3D – Blender

- **Outils** : Blender 3.x pour la création de tous les assets 3D (map, personnages, objets, armes, éléments de décor). 
 **Intégration** : import des fichiers `.glb` via `SceneLoader.ImportMesh` dans Babylon.js, organisation en dossiers `assets/models` et `assets/textures`.  
- **Optimisations** : réduction de la topologie, utilisation de LOD, création d’atlas de textures pour minimiser les appels GPU, 
nettoyage des données non utilisées (vertex groups, modifiers appliqués).   

![blender](https://github.com/user-attachments/assets/c9ac5f70-f94b-4838-8273-052e53c9424b)   



## 5. Modules et responsabilités

### 5.1 UI

- **MainMenu** (`ui/mainMenu.js`)  
  - Affiche logo, boutons (Jouer, Options)  
  - Callback `onPlayButtonClicked` pour passer en jeu  
- **LoadingScreen** (`ui/loadingScreen.js`)  
  - Affiche barre de progression chargement ressources  
- **LevelSelector** (`ui/levelSelector.js`)  
  - Liste des niveaux, sélection manuelle  
- **FPS Display & Boussole** (`ui/fpsDisplay.js`, `ui/compass.js`)  
  - HUD en overlay  
- **Tutorial & WelcomePage** (`ui/tutorial.js`, `ui/welcomePage.js`)  
  - Messages et instructions au premier lancement


### 5.2 Gestion de la scène

- **environment.js**  
  - Génère terrain, skybox, lumière  
- **mapGestion.js**  
  - Découpe la map en tuiles, chargement dynamique pour optimiser performance  
- **visualEffects.js**  
  - Particules de poussière, fumée, etc.  
- **PurpleStorm** (`storm/PurpleStorm.js`)  
  - Tempête dynamique : zones de danger, effets visuels et sonores


### 5.3 Entités et IA

- **Player** (`joueur/player.js`)  
  - Création de mesh, collision (ellipsoïde), mouvement (WASD, souris)  
- **Animations** (`joueur/animations.js`)  
  - Blend trees (idle, marche, tir, etc.)  
- **EnnemiAI** (`ennemis/EnnemiAI.js`)  
  - Comportements “seek/arrive/wander”  
- **AmiAI** (`amis/AmiAI.js`)  
  - Suivi du joueur, assistance au combat


### 5.4 Armement

- **balles.js**  
  - Création de projectiles, détection de collisions, application de dégâts

### 5.5 Événements et contrôles (BUG)

- **controls.js**  
  - Abstraction des événements clavier/souris/tactile  
  - Liaison aux actions du joueur et de l’UI

### 5.6 Gestion des niveaux

- **levelManager.js**  
  - Méthodes `loadLevel(levelId)`, `nextLevel()`, `restartLevel()`  
- **LevelX.js**  
  - Définition des objectifs, positions ennemis/allies par niveau

### 5.7 Configuration

- **gameConfig.js**  
  - Objet unique `GAME_CONFIG` regroupant HERO, ENNEMIS, ARMES, etc.

## 6. Flux d’exécution
![diagram_dreamfall](https://github.com/user-attachments/assets/fd21b675-2224-4553-9407-8b7e4fccfdc1)


## 7. Décisions de conception

- **Modularité forte** : séparation claire des responsabilités (IA, scène, UI)  
- **Centralisation de la config** (`gameConfig.js`) pour éviter les “magic numbers”  
- **Chargement dynamique** des tuiles pour maintenir un framerate constant  
- **Abstraction des contrôles** pour prise en charge clavier/souris ou manette  
- **Injection de callbacks** pour découpler écrans et logique  
- **Pattern Factory** via fichiers `LevelX.js` agissant comme producteurs de données

## 8. Pistes d’évolution
- **Support multijoueur** via WebRTC/Socket.io
- **Version Mobile**  Commencé mais manque de temps
  ![emulatoriPhone16proMax](https://github.com/user-attachments/assets/5be8924a-bd8c-48a0-8fab-4b5c6479d3b9)


## 9. Conclusion

Cette architecture fournit une base solide et extensible pour notre jeu Babylon.js. L’ajout de la modélisation Blender, combiné à la modularité et à la centralisation de la configuration,
facilite la maintenance et l’évolution du projet. 

