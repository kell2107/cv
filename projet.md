# Visualisation de densité de données avec D3.js ("Density Contours")

**Description**

Mon projet consistera à créer une visualisation interactive de densité de points avec la bibliothèque **D3.js**.  
L’objectif est de représenter la concentration de données (par exemple des coordonnées géographiques ou des événements) sous forme de contours colorés, permettant d’identifier visuellement les zones les plus denses.

Inspiré du projet officiel : [D3 Density Contours](https://observablehq.com/@d3/density-contours)

**Outils et technologies**

- **HTML / CSS / JavaScript (ES6)**  
- **D3.js v7** pour la création des contours de densité et la gestion des graphiques SVG  
- **GitHub Pages** pour héberger le projet en ligne   

**Objectifs**

- Manipuler des données visuelles avec D3.js  
- Comprendre la fonction `d3.contourDensity()`  
- Travailler avec des échelles de couleurs et des axes  
- Développer une première datavisualisation interactive  

**Données utilisées**

Les données seront d’abord simulées (points aléatoires) pour tester le rendu visuel.  
Ensuite, elles pourront être remplacées par de vraies données ouvertes sur la Ville de Paris ou l’Île-de-France, comme la localisation :
- des stations de métro ou de vélos en libre-service,  
- des équipements publics (bibliothèques, musées, parcs),  
- ou encore des points d’intérêt urbains (cafés, commerces, lieux culturels).

**Intérêt du projet**

Ce projet montre comment le code peut transformer des données brutes en images lisibles et esthétiques.  
Il met en valeur l’importance de la visualisation de données pour mieux comprendre les dynamiques spatiales et sociales en milieu urbain.

**Étapes de réalisation**

1. Étudier l’exemple officiel sur ObservableHQ  
2. Créer un fichier `index.html` et inclure D3.js  
3. Générer un ensemble de points aléatoires  
4. Utiliser `d3.contourDensity()` pour calculer les zones de densité  
5. Créer une échelle de couleurs pour les différentes intensités  
6. Publier le projet sur GitHub 

**Pour aller plus loin**

- Documentation officielle D3.js : [https://d3js.org/](https://d3js.org/)  
- Tutoriel : [ObservableHQ Density Contours](https://observablehq.com/@d3/density-contours)  
- Exemple de données ouvertes que je pourrais utiliser : [https://data.gouv.fr](https://data.gouv.fr) et [https://opendata.paris.fr](https://opendata.paris.fr)

**Pourquoi ce choix ?**

J’ai choisi ce projet car il illustre concrètement comment les données peuvent devenir visuelles et intelligibles grâce au code.  
Il combine programmation, design et exploration urbaine, trois aspects essentiels du numérique aujourd’hui.  
Ce projet permet aussi d’explorer la ville de Paris et sa région à travers une approche graphique et interactive.

**Étape suivante (prototype)**

Dans une version ultérieure, je souhaite personnaliser entièrement le rendu graphique (couleurs, styles, échelles) et intégrer des données réelles librre d'acces de la ville de paris.  
L’objectif sera de représenter la **densité de fréquentation ou de points d’intérêt dans Paris et l’Île-de-France**, afin d’explorer les dynamiques de mobilité et d’activité urbaine à travers la visualisation de données.

**(intro + évolution + améliorations)**
Introduction

À la base, je voulais réaliser une visualisation de densité uniquement avec D3.js, inspirée de l’exemple officiel Density Contours. L’idée était de représenter la concentration de points sous forme de contours colorés : d’abord avec des données simulées pour tester la méthode, puis avec des données réelles ouvertes de Paris.

Mais en avançant, je me suis rendu compte que les contours, affichés seuls sur un fond blanc, restaient assez abstraits. Sans repères géographiques, il devenait difficile de situer précisément les zones les plus denses. J’ai donc décidé de modifier ma trajectoire : comme mes données représentaient des stations Vélib à Paris, j’ai intégré un fond de carte Leaflet/OpenStreetMap pour donner un contexte spatial clair. Ensuite, j’ai amélioré le projet progressivement avec un peu d’interactivité et une version responsive.

**Ressources et exemples utilisés**

Exemple officiel D3 Density Contours (ObservableHQ)
Documentation de d3.contourDensity()
D3 Graph Gallery (exemples densité 2D)
Dataset Vélib open data : velib-disponibilite-en-temps-reel.csv
Leaflet + OpenStreetMap

**Étapes de réalisation et prototype**

**testprojet.html — Première version fonctionnelle avec D3**

**Objectif : afficher une densité sur les stations Vélib.**

**Ce que j’ai fait :**

Chargement du CSV Vélib (d3.dsv avec séparateur ;).
Extraction et conversion des coordonnées "Coordonnées géographiques" → lat/lon.
Création des échelles x et y.
Calcul et affichage de la densité avec d3.contourDensity().
Ajout des points des stations par-dessus.

**Résultat : densité correcte sur données réelles, mais sans carte de fond.**

**Partie complexe où j’ai utilisé l’IA sur l'ensemble des versions:**

La superposition Leaflet derrière / D3 devant avec gestion du z-index, des positions absolues et des conflits d’événements (pointer-events).

**Résultat : densité lisible directement sur la carte de Paris**

**diagramme de flux**
---
config:
      theme: redux
---
flowchart TD

    A[Chargement de la page HTML]
    
    B[Création du SVG D3]
    
    C[Chargement du CSV Vélib]
    
    D[Extraction lat / lon]
    
    E[Filtrage des données valides]
    
    F[Création des échelles x / y]
    
    G[Calcul de la densité<br/>contourDensity]
    
    H[Création de l'échelle de couleurs]
    
    I[Affichage des contours de densité]
    
    J[Affichage des points stations]

    A --> B --> C --> D --> E --> F --> G --> H --> I
    G --> J



