# Gestionnaire de films

Projet réalisé en R dans le cadre du TD5 (L3 MIAGE, Université Côte d'Azur).
Il explore la **décomposition en valeurs singulières (SVD)** à travers deux applications : la compression d'images et la recommandation de films.

## Contenu

1. **Approximation de rang k** : meilleure approximation d'une matrice par une matrice de rang k, et distance (norme de Frobenius) entre la matrice et son approximation.
2. **Compression d'image** : approximation de l'image `cameraman.png` en niveaux de gris pour différentes valeurs de k.
3. **Énergie conservée** : calcul de l'énergie d'une matrice (norme de Frobenius au carré), comparaison avec la somme des carrés des valeurs singulières, et recherche du plus petit k conservant 90 %, 95 % et 99 % de l'énergie.
4. **Système de recommandation** : prédiction des notes manquantes d'une matrice utilisateurs × films par SVD de la matrice centrée, puis recommandation des meilleurs films non vus pour un utilisateur donné.

## Fichiers

| Fichier | Rôle |
|---|---|
| `TD5.qmd` | Document Quarto avec le code et les commentaires |
| `cameraman.png` | Image utilisée pour la compression |
| `Films.csv` | Matrice de notes (utilisateurs × films) |

## Utilisation

Prérequis : R, [Quarto](https://quarto.org/) et le package `png`.

```r
install.packages("png")
```

Place `cameraman.png` et `Films.csv` dans le même dossier que `TD5.qmd`, puis génère le rendu :

```bash
quarto render TD5.qmd
```

Le résultat est un fichier HTML autonome (`TD5.html`).

## Exemple

```r
Recommender_films(1, 5)  # les 5 meilleurs films non vus pour l'utilisateur 1
```

## Limites

Le RMSE est calculé sur les mêmes notes que celles utilisées pour construire le modèle (pas de jeu de test séparé). Il mesure donc la qualité de la reconstruction, pas la capacité réelle du système à prédire des notes inconnues.

## Auteure

Islem Souissi : L3 MIAGE, Université Côte d'Azur
