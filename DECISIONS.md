# Carnet de décisions

| Date | Décision | Motif et limites |
|---|---|---|
| 2026-10-01 | Démarrer avec Kaggle Store Sales. | Données quotidiennes magasin-produit, promotions et calendrier ; l’accès dépend des règles Kaggle. Les stocks réels ne sont pas fournis. |
| 2026-10-01 | Traiter les décisions de stock par simulation. | Délai, coûts et stock historique manquent ; les hypothèses seront affichées et testées en sensibilité. |
| 2026-10-02 | Distinguer date absente et vente nulle. | Les 25 décembre 2013 à 2016 sont absents du train. Retards et moyennes mobiles calculés sur un calendrier quotidien ; aucune cible n’est imputée à zéro. Les lignes aux variables incomplètes sont exclues de l’apprentissage. |
| 2026-10-02 | Retenir 365 jours pour l’apprentissage final. | Après correction, RMSLE moyen local de 0,4038 contre 0,4180 sur historique complet à 14 jours ; 0,4049 contre 0,4191 à 16 jours. L’historique récent améliore chaque pli. Paramètres identiques et mêmes dates à horizon donné. Aucun réglage à partir du test ou du score Kaggle. |
| 2026-10-02 | Documenter la première soumission séparément de la version corrigée. | Première soumission acceptée : 28 512 lignes, score Kaggle 0,60824. Elle utilisait tout l’historique et les anciennes variables retardées. Les erreurs individuelles du test sont inconnues ; chaque score reste associé à sa version soumise. |
| 2026-10-02 | Comparer les erreurs aux baselines par groupe. | RMSLE, MAE, WAPE, biais et volumes par horizon, famille et magasin ; écarts face à la moyenne des quatre semaines. Petits volumes interprétés avec prudence. |
| 2026-10-02 | Ajouter des délais comparés à stock initial fixe. | Scénarios complémentaires avec sept jours de ventes moyennes au départ, indépendamment du délai de 5, 7 ou 10 jours. Stock moyen défini en fin de journée ; conservation des quantités contrôlée. |
| 2026-10-02 | Lire le service avec la quantité commandée et le stock. | Scénario corrigé nominal : environ 97,0 % pour la baseline contre 95,2 % pour LightGBM, qui commande et conserve moins de stock. Résultats pédagogiques sans estimation d’économies réelles. |
| 2026-10-02 | Conserver les CSV existants pendant la vérification. | Notebooks exécutés et sorties actualisées ; exports contrôlés en mémoire. Le CSV de la première soumission reste inchangé ; la cellule d’export de la soumission, désactivée par défaut, permet de produire la nouvelle version. |
| 2026-10-02 | Versionner l’environnement validé. | Dépendances directes fixées dans requirements.txt pour Python 3.12 ; cinq notebooks de travail vérifiés dans l’environnement du projet. |
| 2026-10-02 | Enregistrer la deuxième soumission Kaggle acceptée. | Version corrigée avec 365 jours d’apprentissage et variables en jours calendaires : RMSLE Kaggle 0,58880, contre 0,60824 pour la première version. Réduction de 0,01944 (environ 3,2 %). Résultat confirmé par la capture Kaggle, statut Complete. Les réglages restent fondés sur les validations locales ; les erreurs individuelles du test ne sont pas connues. |
| 2026-10-04 | Préparer la présentation publique du projet. | Mise en forme des tableaux, chemins affichés relatifs, compression sans perte des figures et export de cinq graphiques agrégés pour le README. Les cinq notebooks de travail sont réunis dans le notebook public `00_projet_complet.ipynb`, exécutable seul depuis les fichiers bruts. Données et CSV exclus ; résultats numériques et calculs conservés. |
| 2026-10-22 | Alléger les figures du notebook public. | Les 66 figures sont réduites à 256 couleurs : 4,7 Mo d’images au lieu de 10,3 ; notebook de 14,9 à 7,5 Mo pour un affichage plus rapide sur GitHub. Écart minimal de 47 dB (PSNR) avec les originaux, sans différence visible ; code, tableaux et résultats inchangés. |
| 2026-10-22 | Vérifier la reproduction et franciser l’affichage. | Réexécution complète depuis les fichiers bruts dans un environnement neuf : sorties identiques à la version publiée. Nombres, pourcentages, dates et axes des figures au format français ; imports inutiles et définitions en double retirés ; figures toujours réduites à 256 couleurs. |
| 2026-10-22 | Diagnostiquer l’écart entre validation locale et score Kaggle. | La chaîne de soumission rejouée sur les 16 derniers jours connus donne un RMSLE de 0,430 : pas d’erreur de code. Le test couvre la rentrée scolaire (16-31 août) ; avec 365 jours d’historique, le jour de l’année propage le pic d’août 2016 à 65 séries inactives depuis plus d’un an (environ 8 unités prévues par jour). Ordre de grandeur estimé : de 0,43 à 0,51 si ces séries vendent zéro. Les plis locaux ne couvrent pas cette période ; le modèle est inchangé dans cette version. |

---

**Auteur : Abdoulaye KONE**  
*Portfolio Data Science - Prévision des ventes et simulation de stock*
