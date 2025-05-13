# Détection d’anomalies de souscription et de gestion des contrats d’assurance

## 1. Contexte métier  
La Direction du Contrôle Interne d’Allianz doit garantir le respect des règles de souscription et de gestion de contrats (Particulier, Entreprise, Santé, Vie…).  
Votre mission : simuler un cas réel en développant, de bout en bout, un prototype d’algorithme d’anomalie qui :
- Vérifie automatiquement la conformité des nouveaux contrats (attributs manquants, tarifs hors-grille, couvertures incompatibles…).  
- Signale les comportements potentiellement frauduleux (montants anormaux, fréquence inhabituelle de souscriptions, résiliations soudaines).  

## 2. Objectifs du projet  
1. **Collecte & simulation des données**  
   - Générer un jeu de données synthétique (10 000 contrats) avec :  
     - Identifiant client, type de produit, date de souscription, montant prime, garanties, localisation, statut sinistre.  
   - Ou exploiter un jeu de données open source « insurance ».

2. **Exploration & feature engineering**  
   - Nettoyer et consolider les données (gestion des valeurs manquantes, encodage catégoriel, normalisation).  
   - Extraire des indicateurs métier :  
     - Âge du contrat, délai souscription–sinistre, fréquence de résiliation, ratio primes/sinistres.  

3. **Détection d’anomalies CPU-only**  
   - Approches **unsupervised** : Isolation Forest, One-Class SVM, Autoencoder dense (PyTorch CPU).  
   - Méthodes **statistiques** : score de Mahalanobis, clustering DBSCAN.  
   - Comparer sensibilité (recall) et précision (precision) sur un sous-ensemble labellisé (5 % anomalies injectées).

4. **Évaluation & tuning**  
   - Métriques : ROC–AUC, Precision@K, F1-score sur anomalies rares.  
   - Optimisation hyperparamètres : nombre d’arbres, taille encodeur, seuils.

5. **Explainability & reporting**  
   - Utiliser SHAP pour la contribution des features.  
   - Visualisations : distributions, courbes de score, heatmaps.  
   - Dashboard statique avec Plotly + Dash (CPU-only).

6. **Packaging & REST API**  
   - Docker + FastAPI (Uvicorn) :  
     - Endpoint `/predict` recevant un JSON de contrat, renvoyant un score d’anomalie + explications.  
   - Documentation Swagger.

## 3. Compétences visées  
- Anomaly Detection avancé (Autoencoder, Isolation Forest, Mahalanobis).  
- Machine Learning CPU-only (optimisation PyTorch).  
- Explainable AI (SHAP).  
- MLOps léger (Docker, FastAPI).  
- Data Engineering (simulation, pipelines).

## 4. Contraintes techniques  
- **100 % CPU**.  
- **Zéro coût** (open source).  
- **Local & reproductible**.

## 5. Planning (1 semaine)

| Jour | Tâches |
|:----:|:-------|
| **1** | Génération / ingestion des données<br>Arborescence du repo & README |
| **2** | Cleaning & feature engineering<br>Notebook EDA |
| **3** | Baselines : Isolation Forest, Mahalanobis<br>Évaluation initiale |
| **4** | Autoencoder PyTorch CPU<br>Entraînement & validation |
| **5** | Tuning hyperparamètres<br>Métriques avancées |
| **6** | Explainability (SHAP, visualisations)<br>Dashboard Dash |
| **7** | Docker + FastAPI<br>Rapport final & slides |

## 6. Livrables  
- Repo GitHub structuré.  
- Notebook Jupyter complet.  
- Dashboard Dash exportable.  
- Image Docker + API Swagger.  
- Document de synthèse + slides.
