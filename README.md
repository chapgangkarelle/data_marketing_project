# data_marketing_project

# TP1 : EDA & Nettoyage

##  Contexte du Projet

L'objectif de ce projet est de réaliser une **Analyse Exploratoire des Données (EDA)** et un nettoyage approfondi des données extraites du CRM de l'entreprise **Lumina & Co**. 

##  Données utilisées

Le projet s'appuie sur deux fichiers sources :

* `customers.csv` : Profils agrégés par client (pays, dates de premier/dernier achat, métriques de dépenses).
* `transactions.csv` : Historique transactionnel ligne par ligne (identifiants de factures, codes produits, quantités, prix unitaires).

---

## 🛠 Structure de la démarche

### Étape 1 : Chargement & Data Quality Report

Avant toute modification, un audit de la qualité des données est réalisé pour documenter les biais visibles :

* **Volumétrie** : Nombre de clients, de transactions et période temporelle couverte.
* **Valeurs manquantes** : Identification des colonnes incomplètes et calcul des proportions.
* **Types de données** : Vérification de la cohérence entre les types attendus et observés.
* **Doublons** : Identification des lignes redondantes.

### Étape 2 : Détection et traitement des anomalies

Traitement rigoureux des incohérences détectées dans le CRM :

* **Transactions** : Gestion des `customer_id` manquants, traitement des quantités négatives (retours), analyse des prix nuls et identification des codes produits atypiques (frais de port, etc.).
* **Clients** : Vérification de la cohérence chronologique des achats et traitement des valeurs aberrantes (*outliers*) sur les dépenses et fréquences via des techniques de clipping (écrêtage).

### Étape 3 : Analyse Exploratoire (EDA) orientée Marketing

Analyse statistique et visuelle pour répondre aux problématiques business :

* **Distribution des achats** : Analyse de la taille des paniers et application de la **Loi de Pareto** (déterminer le % de clients générant 80% du CA).
* **Saisonnalité** : Étude des séries temporelles pour identifier les pics de vente et la stabilité des patterns d'achat d'une année sur l'autre.
* **Géographie** : Analyse de la répartition spatiale et identification des biais (ex: surreprésentation du Royaume-Uni).
* **Relations entre variables** : Étude des corrélations RFM (Récence, Fréquence, Montant) pour détecter des segments naturels de clients.

### Étape 4 : Formulation des hypothèses marketing

Synthèse des observations sous forme d'hypothèses actionnables pour la stratégie de Lumina & Co

## Installation et Utilisation

### Prérequis

* Python 3.8
* Pandas
* Matplotlib / Seaborn
* NumPy

### Exécution

1. Clonez le dépôt.
2. Placez les fichiers `customers.csv` et `transactions.csv` à la racine.
3. Exécutez le notebook ou le script principal pour générer le rapport de qualité et les visualisations.


## Visualisations marquantes

* **Heatmap de corrélation** pour les liens entre variables RFM.