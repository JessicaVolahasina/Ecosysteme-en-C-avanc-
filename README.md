# Simulation d'écosystème en C avancé
# Simulation d'Écosystème en C

## Objectif du Programme

Ce projet consiste à simuler un écosystème simple où des **proies** et des **prédateurs** interagissent dans un environnement discret.  
L'objectif est d'observer l'évolution des populations dans cet écosystème en appliquant des règles spécifiques comme :
- Les déplacements des animaux,
- La reproduction probabiliste,
- Les interactions proie-prédateur.

Cette simulation peut être utilisée pour explorer des concepts d'écologie, de biologie ou d'algorithmique.

---

## Fonctionnalités principales

1. **Déplacement des animaux** :
   - Les animaux se déplacent dans un environnement torique (les bords de la grille se connectent).
   - Les proies recherchent des cases avec de l'herbe pour regagner de l'énergie.

2. **Gestion de l'énergie** :
   - Les animaux consomment de l'énergie à chaque déplacement.
   - Les prédateurs regagnent de l'énergie en mangeant des proies.

3. **Reproduction** :
   - Chaque animal a une probabilité `p_reproduce` de se reproduire à chaque itération.
   - Lors de la reproduction, un nouvel animal est créé, et l'énergie du parent est divisée entre lui et son enfant.

4. **Interactions proie-prédateur** :
   - Les prédateurs consomment les proies lorsqu'ils se déplacent sur une case où une proie est présente.

5. **Évolution en temps discret** :
   - À chaque itération, tous les animaux :
     - Se déplacent,
     - Potentiellement se reproduisent,
     - Interagissent (prédateurs consomment des proies),
     - Voient leur énergie mise à jour.

---

## Fonctionnement du Programme

### 1. Représentation de l'Écosystème
- L'écosystème est modélisé sous forme de **grille** où chaque case peut contenir :
  - De l'herbe (source d'énergie pour les proies),
  - Une proie,
  - Un prédateur.
- Les animaux sont stockés dans une **liste chaînée** pour un traitement dynamique.

### 2. Déplacement des Animaux
- Chaque animal a une direction aléatoire.
- Le monde est torique : lorsqu'un animal dépasse un bord, il réapparaît de l'autre côté.

### 3. Reproduction
- Chaque animal a une probabilité `p_reproduce` de se reproduire à chaque itération.
- Un nouvel animal hérite des caractéristiques de son parent (même position, direction) avec une énergie initiale égale à la moitié de celle du parent.

### 4. Interactions Proies-Prédateurs
- Les prédateurs peuvent consommer les proies :
  - La proie est supprimée de l'écosystème.
  - Le prédateur gagne l'énergie de la proie.

### 5. Simulation en Temps Discret
- Chaque itération correspond à un "cycle de vie" où les règles ci-dessus sont appliquées à tous les animaux.

---

## Technologies utilisées

- **Langage** : C
- **Structures de données** : Liste chaînée pour modéliser dynamiquement les animaux.
- **Bibliothèque standard C** : Pour la gestion de la mémoire dynamique (`malloc`, `free`) et des nombres aléatoires (`rand`).

---

## Comment exécuter le programme ?

1. Cloner ce dépôt :
   ```bash
   git clone https://github.com/ton-pseudo/simulation-ecosysteme.git

