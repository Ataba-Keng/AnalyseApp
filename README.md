# Analyse Exploratoire - Évaluation Hygiène PME

Application Streamlit pour l'analyse et la visualisation des pratiques d'hygiène des PME à partir d'un fichier CSV.

## Fichiers clés
- [app.py](app.py) — point d'entrée de l'application Streamlit.
- [data_analysis.py](data_analysis.py) — logique d'analyse et calcul des scores (classe [`data_analysis.DataAnalyzer`](data_analysis.py)).
- [visualization.py](visualization.py) — génération des graphiques (classe [`visualization.HygieneVisualizer`](visualization.py)).
- [attached_assets/data_1757344901533.csv](attached_assets/data_1757344901533.csv) — jeu de données utilisé.
- [requirements.txt](requirements.txt) — dépendances Python.

## Fonctionnalités
- Vue d'ensemble des données (comptages, taux de valeurs manquantes).
- Statistiques descriptives et intervalles de confiance pour les pratiques d'hygiène.
- Analyse et visualisation des obstacles rencontrés.
- Analyse des formations reçues et corrélations avec les pratiques.
- Comparaison inter-entreprises et scores composés d'hygiène.
- Visualisations interactives (radar, barres, heatmap, boxplot).

## Installation rapide
1. Créer et activer un environnement virtuel (optionnel mais recommandé)
   - Unix/macOS:
     ```sh
     python -m venv .venv
     source .venv/bin/activate
     ```
   - Windows:
     ```ps
     python -m venv .venv
     .\.venv\Scripts\activate
     ```
2. Installer les dépendances:
   ```sh
   pip install -r requirements.txt
   ```

## Lancer l'application
```sh
streamlit run app.py
```
L'application chargera automatiquement le fichier [attached_assets/data_1757344901533.csv](attached_assets/data_1757344901533.csv).

## Navigation dans l'interface
- "Vue d'ensemble" — métriques générales et distribution par type de produit.
- "Statistiques descriptives" — sorties de [`data_analysis.DataAnalyzer`](data_analysis.py).
- "Visualisations par entreprise" — radar et détails pour une entreprise.
- "Analyse des obstacles" — graphiques et IC.
- "Analyse des formations" — distribution et corrélations.
- "Comparaisons inter-entreprises" — scores et boxplots.

## Remarques et bonnes pratiques
- Le CSV contient certaines valeurs "Inconnu" qui sont traitées explicitement; vérifier la qualité des données avant analyses approfondies.
- Les calculs d'IC utilisent une approche binomiale (voir [`data_analysis.DataAnalyzer`](data_analysis.py)).
- Adapter l'encodage si le chargement du CSV échoue (UTF-8 / latin-1).

## Développement
- Modifier la logique d'analyse dans [data_analysis.py](data_analysis.py).
- Ajouter/adapter des graphiques dans [visualization.py](visualization.py).
- Les changements côté UI se font dans [app.py](app.py).

License: MIT (ajouter un fichier LICENSE si nécessaire).
