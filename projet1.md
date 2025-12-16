 **Ce qui a changé dans testprojet1.html** 
 
 **Ajout d’interaction simple**
Objectif : rendre les stations cliquables.

**Améliorations :**
Conservation des infos complètes dans chaque ligne (return d).
Points plus visibles (r=4).
Clic sur une station → alerte affichant le nom.

**Résultat : exploration station par station.**

**Diagramme de flux**

flowchart TD

    A[Chargement de la page HTML]
    
    B[Création du SVG D3]

    C[Chargement du CSV Vélib]
    
    D[Extraction lat / lon]
    
    E[Stockage des données complètes]
    
    F[Filtrage des données valides]
    
    G[Création des échelles x / y]
    
    H[Calcul de la densité]
    
    I[Affichage des contours]
    
    J[Affichage des points stations]
    
    K[Clic sur un point]
    
    L[Affichage alerte station]

    A --> B --> C --> D --> E --> F --> G --> H --> I
    H --> J --> K --> L

