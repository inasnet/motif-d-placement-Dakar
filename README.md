# Analyse des déplacements et prédiction des motifs à Dakar

Projet PySpark consacré à l'étude de la mobilité dans l'agglomération de Dakar à partir d'une enquête de déplacements.

## Objectifs

- Nettoyer et structurer les données de l'enquête.
- Décrire les modes de transport, les motifs, les durées et les horaires des déplacements.
- Étudier la répartition des flux entre les zones de l'agglomération.
- Construire un modèle de classification du motif de déplacement.

## Données

La table source contient 45 605 déplacements et 33 variables : identifiants des ménages et des individus, zones de départ et d'arrivée, horaires, modes de transport, motifs, coûts, poids d'extrapolation et caractéristiques individuelles.

Le référentiel géographique associe les strates aux communes.

## Méthodologie

### Nettoyage et préparation

Le pipeline définit un schéma explicite, harmonise les libellés, traite les codes particuliers et décode les heures au format HHMM, y compris après minuit. Il applique des contrôles de cohérence, conserve les rejets avec leur motif, traite les coûts atypiques par mode et supprime les doublons sur la clé métier.

La jointure du référentiel et la création de variables dérivées complètent cette préparation. Les hypothèses de codage sont précisées dans le notebook.

### Analyse exploratoire

L'analyse utilise les poids d'extrapolation pour étudier les parts modales, les motifs, les durées, les profils horaires et la matrice origine-destination. Elle distingue les effectifs observés des estimations pondérées.

### Modélisation

La classification utilise un Random Forest avec encodage des variables catégorielles et imputation des variables numériques. L'évaluation comprend l'accuracy, la précision, le rappel, le F1, une matrice de confusion et une comparaison à la classe majoritaire.

## Organisation du dépôt

| Fichier | Contenu |
| --- | --- |
| `deplacements_pyspark_corrige.ipynb` | Nettoyage, analyse exploratoire et modélisation |
| `donnees_csv/deplacement.csv` | Table des déplacements |
| `donnees_csv/strate_commune.csv` | Référentiel des strates et communes |

## Utilisation

Le notebook est configuré pour Google Colab.

1. Importer le fichier `deplacements_pyspark_corrige.ipynb` dans Colab.
2. Exécuter les cellules dans l'ordre.
3. Fournir le fichier source `donnees_deplacement_PSpark_2026_1.xlsx` lorsque la cellule de chargement le demande.
4. Récupérer les fichiers produits à la fin du notebook.

Les deux CSV intermédiaires sont disponibles dans le dépôt. Pour les utiliser directement, adapter les cellules de chargement et les chemins. Le fichier Excel source n'est pas inclus.

## Technologies

Python, PySpark, Spark MLlib, pandas, Matplotlib et Seaborn.
