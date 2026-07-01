# Correctifs de la page Compétences

## Cause des problèmes

- Les deux panneaux utilisaient la grille générique `dual-panel-grid` avec une répartition très asymétrique (`1.3fr / .7fr`) et aucun composant de panneau spécifique pour uniformiser le padding des titres.
- La classe générique `soft-grid`, partagée avec la page À propos, imposait trois colonnes même dans un panneau étroit. Les textes étaient donc comprimés et les retours à la ligne artificiels.
- Les cartes d’outils utilisaient de simples éléments `span`, sans largeur minimale, sans zone d’icône normalisée et sans règle d’égalité de hauteur.
- Les anciens SVG étaient des pictogrammes personnalisés avec un fond sombre intégré. Sur les cartes sombres, certains semblaient vides ou mal cadrés. Plusieurs utilisaient aussi du texte SVG dépendant du rendu des polices.
- Dans l’archive, les chemins étaient exacts et les fichiers existaient. En production, le seul risque de 404 venait du fait que le nouveau dossier `assets/images/icons/` devait être envoyé avec les fichiers HTML/CSS. La nouvelle version conserve toutes les ressources localement et vérifie chaque référence.

## Choix appliqués

- Nouveau composant partagé `.section-panel` pour les panneaux de la page.
- Nouvelle grille `.competency-panels-grid` équilibrée sur desktop et empilée sur tablette/mobile.
- Cartes soft skills avec `auto-fit` et largeur minimale lisible.
- Cartes outils avec une zone d’icône fixe, un texte flexible et une hauteur homogène.
- Logos de marque stockés dans `assets/images/icons/brands/`.
- Icônes fonctionnelles homogènes stockées dans `assets/images/icons/ui/`.
- Textes alternatifs ajoutés à toutes les images de la page.
- Breakpoints vérifiés à 1440 px, 820 px et 390 px sans débordement horizontal.
