# Recherche d'images par la forme — Implémentation de l'article "Shape-based image retrieval using Generic Fourier Descriptor"

## Objectif du projet:

Ce projet a pour but de reproduire, implémenter et évaluer la méthode de recherche d’images basée sur la forme proposée dans l’article **"Shape-based image retrieval using Generic Fourier Descriptor"** de **Zhang et Lu (2002)**. Ce travail s’inscrit dans le cadre du cours de traitement d’images à **Sorbonne Université**.

L’objectif est double :
- Appréhender la méthode du **Generic Fourier Descriptor (GFD)** telle que formulée dans l’article de référence.
- Concevoir un prototype en Python permettant de tester cette approche sur une base d’images de formes.

## Contexte scientifique:

La **recherche d’images par le contenu (CBIR)** est une thématique majeure en vision par ordinateur. Elle vise à retrouver des images similaires à partir de caractéristiques visuelles, sans recourir aux métadonnées textuelles.

Parmi les types de caractéristiques exploitables (couleur, texture, forme), la **forme** est particulièrement pertinente pour des applications telles que :
- la reconnaissance d’objets industriels,
- la classification d’organismes biologiques,
- l’analyse biométrique (empreintes, silhouettes),
- la recherche dans les bases de logos ou pictogrammes.

Les auteurs Zhang et Lu proposent un descripteur de forme appelé **Generic Fourier Descriptor**, qui présente plusieurs avantages :
- invariance aux **transformations géométriques** (translation, rotation, mise à l’échelle),
- capacité à capturer à la fois les **caractéristiques globales** et **locales** des formes,
- efficacité computationnelle et facilité d’implémentation.

## Méthodologie :

Ce projet suit une pipeline inspirée directement de l’article :

1. **Prétraitement des images**
   - Binarisation et extraction des objets d’intérêt
   - Détection du contour
   - Centrage et normalisation de la forme

2. **Calcul du descripteur GFD**
   - Conversion de la forme en coordonnées polaires centrées
   - Application de la **transformée de Fourier bidimensionnelle (2D-DFT)**
   - Sélection et normalisation des coefficients pour créer un vecteur caractéristique

3. **Système de recherche**
   - Comparaison des vecteurs GFD entre l’image requête et les images de la base
   - Calcul d’une distance (euclidienne ou autre)
   - Classement des résultats par similarité décroissante

4. **Évaluation**
   - Application sur une base d’images de formes (ex : MPEG-7 CE Shape Dataset)
   - Analyse de la **précision** et de la **robustesse** aux transformations géométriques

