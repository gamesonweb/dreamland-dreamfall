[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/tcwhlYLU)

# Dreamfall

Un jeu d'action-aventure 3D développé avec BabylonJS pour la compétition Game On Web 2025.

## Aperçu

Dreamfall est une aventure immersive en 3D où les joueurs incarnent une licorne à travers différents niveaux, affrontent des ennemis, recrutent des alliés et explorent un monde dynamique. Le jeu propose des mécaniques de combat, une progression du personnage et une narration captivante à travers plusieurs niveaux uniques.

## Fonctionnalités

- Monde 3D immersif : Explorez des environnements variés avec des cycles jour/nuit et des effets météo dynamiques  
- Système de combat : Affrontez vos ennemis à l’aide de projectiles et de mécaniques variées  
- Système d’alliés : Recrutez des personnages amicaux pour vous aider dans votre quête  
- Progression : Gameplay basé sur des niveaux avec des objectifs et des défis uniques  
- Environnement dynamique : Interagissez avec des PNJ, des systèmes de circulation et une météo changeante  
- Combats de boss : Faites face à des ennemis puissants avec des mécaniques et stratégies spécifiques  

## Niveaux du jeu

1. Tutoriel : Apprenez les commandes de base et les mécaniques du jeu (important de faire le tutoriel sinon les controls ne fonctionnement pas !!!)
2. La Rencontre : Trouvez et devenez ami avec Ray le chien  
3. Exploration : Trouvez les bananes et recrutez-les comme alliés  
4. Le Magicien : Trouvez le magicien pour obtenir le pouvoir magique (de pouvoir tirer des balles)
5. La Catastrophe : La reine est kidnappé, les couleurs de la villes ont disparu, le peuple est malheureux, recuperer les couleurs pour rendre une situation stable sur la ville
6. La Menace : Éliminez les pizzas pour sauver la ville  
7. Le Combat Final : Ville ravagé par la tempête, il faut donc construire une fusée.

## Contrôles

- Mouvement : Touches WASD / ZQSD  
- Viser / Regarder autour : Mouvement de la souris  
- Tirer : Bouton gauche de la souris  
- Interagir : Touche E  
- Pause : Touche ÉCHAP  

## Stack Technique

- Moteur : BabylonJS 7.5+  
- Système de build : Vite  
- Animations : GSAP  
- Physique : Physique intégrée de BabylonJS  
- Interface utilisateur : Composants HTML/CSS personnalisés et BabylonJS GUI  
- Audio : WebAudio API

## Architecture Technique

### Systèmes principaux
- Gestion des scènes : Chargement modulaire des niveaux avec chargement progressif des assets  
- Système de balle + tir 
- Système d’IA (wander + seek)
- Détection de collisions  

### Optimisations des performances
- Chargement des assets : Chargement asynchrone avec priorisation et mise en cache  
- Gestion mémoire : Libération des meshes
- Optimisation des glbs sur Blender
- Suppression des particules inutiles
- Reduction de la distance des caméras : 30

### La v1 de notre jeu sans optimisation : 
Lien : game-onweb.vercel.app // VIELLE VERSION POUR VOIR LA DIFFERENCE AU NIVEAU PERFORMANCE SUR LA VERSION FINAL

### Lien jeu final ici :
Lien : babylon-js-final-babygame.vercel.app
// VERSION FINAL MAIS DES AMELIORATION SONT OBLIGATOIRE POUR LE GAMEONWEB
// CHANGER LES TEXTE ('ANCIEN TEXTE QUI N'ONT PAS ETE MODIFIER')
// LA MAP QUI VA ETRE UTILISER ET QUI VA DEVOIR MONTRER OU SONT LES ENNEMI, LES BANANES, LE CHIEN OU LA REINE.

## Installation

```bash
# Cloner le dépôt
git clone https://github.com/your-username/dreamfall.git

# Se rendre dans le dossier du projet
cd dreamfall

# Installer les dépendances
npm install

# Lancer le jeu
npm run dev
```

## Prérequis

- Navigateur moderne avec support WebGL (Chrome recommandé !!!!!)
- Clavier et souris
- Avoir un bon Ordinateur et surtout récent !

## 📹 Ressources & Tutoriel vidéo
Voici l'ensemble de nos vidéos :
- [Level 1]([https://youtu.be/T_Fbgmi4p40](https://youtu.be/xqEyRhz6bgg?si=Y5GKklcliH2hG32n))
- [Level 2]([https://youtu.be/CUS6Bx78IPM](https://youtu.be/HGzp4-O-2x4?si=gcUon4Uafk-jHaJV))
- [Level 2b]([https://youtu.be/d4j3HttVcE4](https://youtu.be/7makHjATyNY?si=I4kGkyA2aZEakX_W))
- [Level 3]([https://youtu.be/Tdp7TgrVo8I](https://youtu.be/AsiOycLtfKA?si=06is7obfa3caF9cL))
- [Level 4]([https://youtu.be/d7kMfUK0dEk](https://youtu.be/-wW5vnw3g28?si=kIsG5TZGaD8yTlnL))
- [Level 5]([https://youtu.be/mZAOfvDtpfE](https://youtu.be/p-ooJLaYe2c?si=7Js_dMYILtBvCIOq))
- [Level 6]([https://youtu.be/LHLuoezAYkA](https://youtu.be/xzgNnj7J7Ig?si=DQlPYEejMvNzN34S))
- [Gameplay complet du jeu ]([https://youtu.be/jrhd8IdCYdw](https://youtu.be/LMPR1_-Krlg?si=m8z27Ii_quaJ-ecn))



## Assets
### Modèles GLB – Personnages

- **Banane** : [https://poly.pizza/m/TFlEjNafR1](https://poly.pizza/m/TFlEjNafR1)  
- **Dog** : [https://poly.pizza/m/1gXKv15ik8](https://poly.pizza/m/1gXKv15ik8)  
- **Licorne** : [https://poly.pizza/m/TLsBUOdTr7](https://poly.pizza/m/TLsBUOdTr7)  
- **Cuisse de poulet** : [https://poly.pizza/m/JdkTgIzJZX](https://poly.pizza/m/JdkTgIzJZX)  
- **Cool Egg** : [https://poly.pizza/m/WnzvqAXBVK](https://poly.pizza/m/WnzvqAXBVK)  
- **Poo (caca)** : [https://poly.pizza/m/03djWQlJue](https://poly.pizza/m/03djWQlJue)  
- **Magicien** : [https://poly.pizza/m/dEuyzEgrF4](https://poly.pizza/m/dEuyzEgrF4)  
- **Reine** : [https://poly.pizza/m/MecWbYSEVe](https://poly.pizza/m/MecWbYSEVe)  
- **Ennemi IA** : [https://poly.pizza/m/EMoKrFEBkc](https://poly.pizza/m/EMoKrFEBkc)  
- **BigBoss** : [https://poly.pizza/m/Q0ZWVssZCg](https://poly.pizza/m/Q0ZWVssZCg)

### Modèles GLB – Bâtiments

- **Building A** : [https://poly.pizza/m/EL3ePInr1N](https://poly.pizza/m/EL3ePInr1N)  
- **Building B** : [https://poly.pizza/m/5XG9i3QzlT](https://poly.pizza/m/5XG9i3QzlT)  
- **Building C** : [https://poly.pizza/m/g15lpKh4li](https://poly.pizza/m/g15lpKh4li)  
- **Building D** : [https://poly.pizza/m/bbH2Bg73qM](https://poly.pizza/m/bbH2Bg73qM)  
- **Building E** : [https://poly.pizza/m/otRsYa6pan](https://poly.pizza/m/otRsYa6pan)  
- **Building F** : [https://poly.pizza/m/qOhhGLftam](https://poly.pizza/m/qOhhGLftam)  
- **Building G** : [https://poly.pizza/m/7lMEpT2ICD](https://poly.pizza/m/7lMEpT2ICD)  
- **Building H** : [https://poly.pizza/m/g15lpKh4li](https://poly.pizza/m/g15lpKh4li)  
- **Building I** : [https://poly.pizza/m/T3oyvK6VEU](https://poly.pizza/m/T3oyvK6VEU)

### Modèles GLB – Objets dans le jeu

- **Traffic Light** : [https://poly.pizza/m/aYC3t5ymln](https://poly.pizza/m/aYC3t5ymln)  
- **Dumpster** : [https://poly.pizza/m/QmYKHtUnxb](https://poly.pizza/m/QmYKHtUnxb)  
- **Fence** : [https://poly.pizza/m/aE3GIx8jIH](https://poly.pizza/m/aE3GIx8jIH)  
- **Route** : [https://poly.pizza/m/5BPCPOycxC](https://poly.pizza/m/5BPCPOycxC)  
- **Cage** : [https://poly.pizza/m/TAqDCvxcxd](https://poly.pizza/m/TAqDCvxcxd)

### Modèles GLB – Véhicules

- **Taxi** : [https://poly.pizza/m/u5PhZQ35XG](https://poly.pizza/m/u5PhZQ35XG)  
- **Voiture verte** : [https://poly.pizza/m/vTTTjDoxhV](https://poly.pizza/m/vTTTjDoxhV)  
- **Voiture de police** : [https://poly.pizza/m/Uj7i2vlmir](https://poly.pizza/m/Uj7i2vlmir)

### Sons

- **Epic War** : [https://pixabay.com/music/main-title-epic-war-background-music-333128/](https://pixabay.com/music/main-title-epic-war-background-music-333128/)  
- **Honey Chill Lofi** : [https://pixabay.com/music/beats-honey-chill-lofi-309227/](https://pixabay.com/music/beats-honey-chill-lofi-309227/)

### Images

Toutes les images ont été générées par **ChatGPT**.

## Équipe

Dreamfall a été créé par l’équipe Babygame pour la compétition Game On Web 2025.

