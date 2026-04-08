# Analyse Descriptive et Prédictive des Ventes

## Contexte
Analyse des comportements d'achat d'un retailer e-commerce international 
à partir de données transactionnelles réelles (2010-2011).

## Dataset
- Source : OnlineRetail.csv
- Volume : 541 909 transactions | 38 pays | 8 colonnes
- Nettoyage : 5 268 doublons supprimés, 135 080 valeurs manquantes traitées
- Données propres retenues : 524 878 transactions

## Objectifs
1. Explorer et nettoyer les données transactionnelles
2. Analyser la distribution du chiffre d'affaires par pays et par produit
3. Détecter les outliers (Z-score, IQR)
4. Construire un modèle de régression linéaire pour prédire le CA

## Résultats Clés
- 🇬🇧 Le Royaume-Uni représente 8,16M£ de CA (marché dominant)
- Produit avec le CA moyen/transaction le plus élevé : 
  REGENCY CAKESTAND 3 TIER (86,77£ en moyenne)
- Corrélation Pearson Quantité/CA : **r = 0,91** (très forte)
- Modèle de régression linéaire : **R² = 0,82**  
  → 82% de la variation du CA est expliquée par la quantité vendue
- 520 outliers détectés via Z-score (|Z| > 3)

## Stack Technique
Python | Pandas | NumPy | Scipy | Matplotlib | Seaborn

## Lancer le projet
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1gVd40jfe5Dq8Zsr_cKvdyb6v_-6Zl7Xu?usp=sharing#scrollTo=PGr_1yJLf1-q)
