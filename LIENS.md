# Sources : prévision des ventes et gestion du stock

## Jeu de données principal

- **Kaggle : Store Sales - Time Series Forecasting** : https://www.kaggle.com/competitions/store-sales-time-series-forecasting
  - Ventes quotidiennes d’un distributeur alimentaire, avec magasins, produits, promotions et calendriers.
  - Compte Kaggle et acceptation des règles de la compétition nécessaires au téléchargement.
  - Ne pas publier ou redistribuer les fichiers du concours ; consulter les règles Kaggle avant tout usage ou déploiement public.

## Téléchargement Kaggle

- Documentation officielle de l’API : https://github.com/Kaggle/kaggle-api
- Installation dans l’environnement du projet : `python -m pip install kaggle`
- Après acceptation des règles, configurer les identifiants Kaggle hors du dépôt (par exemple dans `%USERPROFILE%\.kaggle\kaggle.json`). Ne jamais partager ce fichier ni son contenu.
- Commande depuis la racine du projet : `kaggle competitions download -c store-sales-time-series-forecasting -p data/raw`

## Alternative avec licence explicite

- **UCI : Online Retail II** : https://archive.ics.uci.edu/dataset/502/online+retail+ii
  - Transactions en ligne britanniques de 2009 à 2011, sous licence CC BY 4.0 avec attribution.
  - Utile pour agréger les ventes par produit et période, mais ne contient pas de magasin, de stock réel, de rupture ou de délai fournisseur. Ce n’est donc pas le meilleur choix pour notre simulation magasin-produit.

## Références méthodologiques

- Scikit-learn, validation temporelle (`TimeSeriesSplit`) : https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.TimeSeriesSplit.html
- Kaggle Learn, séries temporelles : https://www.kaggle.com/learn/time-series

---

**Auteur : Abdoulaye KONE**  
*Portfolio Data Science - Prévision des ventes et simulation de stock*
