# Jour 4 - Deep Learning, Évaluation et Mise en Production

## Objectif

L'objectif de ce projet est d'appliquer les notions vues pendant le cours :

- séparation des données en train / validation / test
- évaluation rigoureuse d'un modèle
- bootstrap et validation croisée
- choix des métriques selon le besoin métier
- sauvegarde d'un modèle entraîné
- création d'une API de prédiction
- création d'une interface utilisateur simple

Le projet est réalisé sur le dataset Breast Cancer Wisconsin disponible dans scikit-learn.

---

## Dataset

Le jeu de données contient des mesures médicales permettant de prédire si une tumeur est :

- bénigne
- maligne

Caractéristiques :

- 569 observations
- 30 variables numériques
- problème de classification binaire

--
## Étapes réalisées

### 1. Préparation des données

- chargement du dataset
- analyse rapide des dimensions
- séparation train / validation / test
- normalisation avec StandardScaler

### 2. Évaluation par bootstrap

Mise en place d'un rééchantillonnage bootstrap afin d'observer la stabilité des performances du modèle.

### 3. Validation croisée

Utilisation d'une validation croisée stratifiée afin d'obtenir une estimation plus fiable des performances.

### 4. Analyse métier

Calcul :

- matrice de confusion
- précision
- rappel
- F1-score

Ajout d'un coût métier permettant de comparer plusieurs modèles selon l'impact des erreurs.

### 5. Sauvegarde du modèle

Le modèle entraîné ainsi que le scaler sont sauvegardés avec Joblib afin de pouvoir être réutilisés en production.

### 6. API Flask

Création d'une API REST simple permettant d'envoyer les caractéristiques d'un patient et de recevoir une prédiction.

### 7. Interface utilisateur

Création d'une interface Streamlit permettant de tester facilement le modèle sans utiliser l'API directement.

### 8. Comparaison de modèles

Comparaison entre :

- Random Forest
- Perceptron Multi-Couches (MLP)

afin d'identifier le modèle le plus adapté au dataset.

---



Sur ce dataset tabulaire relativement petit, le Random Forest obtient des performances similaires ou supérieures au réseau de neurones tout en étant plus rapide à entraîner.

Cela confirme l'un des points importants du cours : un modèle plus complexe n'est pas forcément le meilleur choix.

---




```

---

## Conclusion

Ce projet permet de couvrir l'ensemble de la chaîne de travail d'un modèle de machine learning :

- préparation des données
- entraînement
- évaluation
- comparaison
- sauvegarde
- mise à disposition via une API et une interface web