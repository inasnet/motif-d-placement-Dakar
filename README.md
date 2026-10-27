# Mobilite et motifs de deplacement a Dakar

Notebook PySpark : nettoyage, analyse exploratoire et prediction du motif de deplacement.

## Fichiers

- `deplacements_pyspark_corrige.ipynb` : notebook du projet.
- `donnees_csv/deplacement.csv` : donnees des deplacements.
- `donnees_csv/strate_commune.csv` : referentiel geographique.

## Execution

Le notebook est configure pour Google Colab. Importer le notebook dans Colab, lancer les cellules dans l'ordre et fournir le fichier Excel source `donnees_deplacement_PSpark_2026_1.xlsx` lors du chargement. Ce fichier Excel n'est pas inclus dans ce depot.

Les CSV intermediaires sont fournis. Leur utilisation directe necessite d'adapter les cellules de chargement et les chemins.

## Verification

Le nettoyage a ete execute localement sur les CSV : 45 605 lignes source, 45 602 lignes conservees et 3 rejets. L'export Parquet a bloque sur la configuration Hadoop sous Windows. L'analyse exploratoire et la modelisation n'ont pas ete validees par cette execution locale.
