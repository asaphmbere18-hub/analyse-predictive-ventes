# Analyse descriptive et prédictive des ventes

## Contexte
Analyse des ventes d'un détaillant e-commerce international (2010-2011) à partir du jeu de données public
Online Retail : nettoyage, statistiques descriptives, détection de valeurs atypiques et régression linéaire.

## Données
| Étape | Lignes |
|---|---|
| Fichier brut (38 pays, 8 colonnes) | 541 909 |
| Après suppression de 5 268 doublons | 536 641 |
| Après écart des retours et des prix nuls (quantité ou prix inférieur ou égal à 0) | 524 878 |

Valeurs manquantes : 135 080 `CustomerID` (remplacés par 0) et 1 454 `Description`.

## Objectifs
1. Explorer et nettoyer les données de transactions
2. Analyser le chiffre d'affaires par pays et par produit
3. Détecter les valeurs atypiques (Z-score, IQR)
4. Mesurer le lien entre quantité et chiffre d'affaires par une régression linéaire simple

## Résultats
- **Royaume-Uni : 8,17 M£ de chiffre d'affaires**, soit 84 % du total (retours déduits). Marché dominant.
- Parmi les 3 produits les plus fréquents, **REGENCY CAKESTAND 3 TIER** a le CA moyen par transaction le plus élevé
  (86,77 £, médiane 25,50 £). La moyenne est tirée par quelques grosses commandes : la médiane est plus fiable.
- Corrélation de Pearson quantité / CA : **r = 0,91**.
- Régression linéaire simple : **R² = 0,82**.
- Valeurs atypiques sur la quantité : **520** par Z-score (|Z| > 3) et **27 111** par IQR.

## Limites
- Le CA d'une ligne vaut quantité x prix unitaire. Le R² de 0,82 est donc en partie mécanique :
  il ne prouve pas que « la quantité explique les ventes », il mesure un lien en partie construit.
- Le modèle n'utilise qu'une seule variable et n'a pas été testé sur des données mises de côté : il décrit, il ne prédit pas.
- Les valeurs atypiques sont nombreuses (27 111 par IQR) : la distribution est très asymétrique,
  ce qui plaide pour résumer les ventes par la médiane plutôt que par la moyenne.
- 135 080 `CustomerID` manquants remplacés par 0 : l'analyse par client n'est pas possible sur ces lignes.

## Stack technique
Python | Pandas | NumPy | SciPy | Matplotlib | Seaborn

## Lancer le projet
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1gVd40jfe5Dq8Zsr_cKvdyb6v_-6Zl7Xu?usp=sharing#scrollTo=PGr_1yJLf1-q)

Dernière mise à jour : 02/11/2026
