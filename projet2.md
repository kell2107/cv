
**Ce qui a changé dans testprojet2.html** 

**Changement de trajectoire : ajout Leaflet statique**

**Objectif : placer la densité dans Paris pour faciliter la lecture.**

Ce que j’ai ajouté :
- Carte Leaflet en fond (OpenStreetMap).
- Carte figée (pas de zoom, pas de drag).
- SVG D3 superposé au-dessus.
- Désactivation des interactions Leaflet pour garder les clics sur D3.
- Alertes enrichies (nom, capacité, bornettes libres).

**diagramme de flux**

flowchart TD

    A[Chargement de la page HTML]
    
    B[Initialisation Leaflet<br/>Carte statique]
    
    C[Création du SVG D3]
    
    D[Chargement CSV Vélib]
    
    E[Extraction lat / lon]
    
    F[Calcul échelles D3]
    
    G[Calcul densité<br/>contourDensity]
    
    H[Affichage contours]
    
    I[Affichage points stations]
    
    J[Clic sur un point]
    
    K[Affichage alerte]

    A --> B --> C --> D --> E --> F --> G --> H
    G --> I --> J --> K
