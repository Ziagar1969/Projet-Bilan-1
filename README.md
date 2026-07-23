# PortFolio Vue

Description
- Petite application Vue présentant des réalisations personnelles (CV en ligne, cahier des charges, espace de commentaires, widget météo).
- Comprend des modales réutilisables (Modale2) et un composant MeteoWidget.

Technologies
- Vue.js (version du projet)
- Vite ou Vue CLI (selon setup)
- HTML / CSS / JavaScript

Fonctionnalités
- Grille responsive de projets (2 colonnes → 1 colonne mobile)
- Modales pour afficher détails et média (image formUdemy.jpg, widget météo)
- Navigation par router (Accueil, Réalisations, Contact)

Prérequis
- Node.js >= 16
- npm ou yarn

Installation
```bash
cd c:\CODE\projet_Vue\portFolio
npm install
```

Lancer en développement
- Vite :
```bash
npm run dev
```
- Vue CLI :
```bash
npm run serve
```

Build pour production
```bash
npm run build
```

Structure importante
- src/views/Nouvelle.vue — page "Réalisations" (ajout du 4ᵉ projet, modales)
- src/components/Modale2.vue — composant modale réutilisable
- src/components/MeteoWidget.vue — widget météo
- src/components/NavigationBar.vue — barre de navigation
- src/assets/img/formUdemy.jpg — image utilisée dans la modale
- src/assets/img/* — autres miniatures et images





Contact
- GitHub : Ziagar1969
