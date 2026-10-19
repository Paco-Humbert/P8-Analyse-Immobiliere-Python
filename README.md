# Analyse du marché immobilier parisien avec Python

**Projet 8 — Parcours Business Intelligence Analyst | OpenClassrooms**

## Présentation

Dans ce scénario pédagogique, un consultant BI de l'ESN Data accompagne l'entreprise « Les plus Beaux Logis de Paris ». La mission consiste à analyser les prix immobiliers parisiens, estimer la valorisation de son portefeuille et étudier une segmentation automatique d'opportunités immobilières.

## Objectifs métier

- Analyser l'évolution des prix immobiliers entre 2017 et 2021.
- Étudier les différences selon la surface, la localisation et le type de bien.
- Construire et évaluer une régression linéaire pour prédire la valeur foncière.
- Estimer la valorisation du portefeuille au 31 décembre 2022 et comparer ses segments.
- Explorer une segmentation en deux groupes avec KMeans pour aider à identifier la nature des biens.
- Comparer plusieurs modèles de régression et expliquer leurs limites.

## Technologies

Python, Jupyter Notebook, pandas, NumPy, Matplotlib, SciPy, scikit-learn et openpyxl.

## Contenu du dépôt

| Fichier | Rôle |
|---|---|
| [Notebook Python](Humbert_Paco_1_Notebook_082026.ipynb) | Exploration, préparation des données, analyses statistiques, modèles et contrôles |
| [Présentation PowerPoint](Humbert_Paco_2_presentation_082026.pptx) | Support de restitution au client |
| [Historique immobilier](historique_immobilier_paris_2017_2021_vdef2.xlsx) | Transactions utilisées pour l'analyse et l'entraînement |
| [Portefeuille d'actifs](portefeuille_actifs%2B%283%29.xlsx) | Biens dont la valeur est à estimer |
| [Échantillon à classer](echantillon_a_classer2.xlsx) | Opportunités utilisées pour la segmentation |

Les cinq fichiers d'origine sont conservés à l'identique. Seuls le README, le fichier de dépendances et le `.gitignore` ont été ajoutés pour préparer le dépôt.

## Démarche

1. Explorer les sources, contrôler les valeurs manquantes et les doublons.
2. Visualiser les tendances des prix au mètre carré et les différences entre arrondissements et types de locaux.
3. Étudier les relations entre variables quantitatives avec les outils statistiques.
4. Encoder les variables catégorielles et séparer les observations en apprentissage et test.
5. Évaluer la régression linéaire, puis estimer la valeur du portefeuille.
6. Construire une segmentation KMeans sur le prix au mètre carré et interpréter les groupes.
7. Comparer la régression linéaire à un arbre de décision, une forêt aléatoire et un Gradient Boosting.
8. Examiner les métriques, les contrôles techniques et les limites de généralisation.

## Résultats enregistrés dans le notebook

| Indicateur | Résultat |
|---|---:|
| Régression linéaire : erreur moyenne en pourcentage (MAPE) sur le test | 9,05 % |
| Régression linéaire : erreur absolue moyenne (MAE) sur le test | 32 821,64 € |
| Régression linéaire : coefficient R² sur le test | 0,982 |
| Valorisation prédite du segment particuliers | 71,22 M€ |
| Valorisation prédite du segment corporate | 97,53 M€ |
| Valorisation totale prédite du portefeuille | 168,75 M€ |
| Segmentation KMeans : score de silhouette | 0,909 |

Le segment corporate présente la valorisation totale prédite la plus élevée. Ces montants sont des estimations issues du modèle, et non des prix de vente constatés.

Ces valeurs sont reprises des sorties déjà présentes dans le notebook. Le projet n'a pas été réexécuté lors de cette préparation pour GitHub.

## Évaluation et limites

La séparation des données conserve 33 % des observations pour le test, avec `random_state=42`. Le découpage est aléatoire et mélange des transactions de 2017 à 2021 : ses métriques ne démontrent pas à elles seules la fiabilité d'une projection au-delà de cette période.

Le notebook discute l'intérêt d'une validation chronologique pour la valorisation au 31 décembre 2022. Cette date correspond à la cible du scénario pédagogique, pas à une estimation du marché actuel.

Les estimations ne prennent pas directement en compte l'ensemble des caractéristiques d'un bien, son état, son occupation ou les changements de marché après 2021.

KMeans produit des groupes selon le prix au mètre carré. Leur attribution à des types de locaux est interprétée à partir d'une référence historique. Le score de silhouette mesure la séparation des groupes ; il ne représente pas un taux de bonne classification du type de bien.

Les modèles complémentaires sont comparés avec plusieurs métriques : MAE, MAPE, RMSE et R². Le choix d'un modèle doit aussi considérer son interprétabilité et sa capacité à extrapoler au-delà de la période d'entraînement.

## Exécuter le projet

Conserver les trois fichiers Excel dans le même dossier que le notebook, sans changer leurs noms. Depuis ce dossier :

```bash
python -m pip install -r requirements.txt
python -m notebook
```

Ouvrir `Humbert_Paco_1_Notebook_082026.ipynb`, sélectionner l'environnement Python utilisé pour l'installation, puis exécuter les cellules dans l'ordre. Le notebook utilise le dossier de travail courant pour charger les données.

Le fichier `requirements.txt` liste les bibliothèques importées ; il ne constitue pas un environnement historique figé avec des versions vérifiées.

## Compétences illustrées

- Préparation et contrôle de données avec pandas.
- Analyse exploratoire et visualisation de données immobilières.
- Statistique descriptive et analyse des corrélations.
- Régression, comparaison de modèles et évaluation des prédictions.
- Segmentation non supervisée avec KMeans.
- Communication des résultats et discussion des limites métier.

## Auteur

Paco Humbert — Projet pédagogique réalisé dans le cadre du parcours Business Intelligence Analyst d'OpenClassrooms.
