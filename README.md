<div align="center">

# Data Integration Case Study
### Campus Tech : le magasin au plus fort chiffre d'affaires est-il le meilleur ?

![Python](https://img.shields.io/badge/Python-3.9%2B-1F3A5F?style=flat-square&logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-nettoyage%20et%20jointures-1F3A5F?style=flat-square)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3%20figures-1F3A5F?style=flat-square)
![Période](https://img.shields.io/badge/p%C3%A9riode-1--28%20avril%202025-4A6572?style=flat-square)

**M1-INF4 · Python Workshop for Data Analysis · Séance 5**

Malik · Jeremy · Aylin · Hiba

</div>

---

## Objectif

Campus Tech est un détaillant fictif d'accessoires et de matériel informatique. Le responsable affirme :

> *« Le magasin avec le plus fort chiffre d'affaires total est le meilleur ; copions son approche partout. »*

Nous intégrons trois sources (commandes, magasins, produits), nettoyons les données, calculons des indicateurs fiables et évaluons cette affirmation pour la période du 1er au 28 avril 2025.

> **Remarque.** Toutes les données sont synthétiques. Les résultats décrivent cet échantillon, pas une entreprise réelle.

---

## Contenu du dépôt

```
.
├── README.md
├── requirements.txt
├── data/                                      # données brutes, jamais modifiées
│   ├── case_sales.csv
│   ├── case_stores.csv
│   └── case_products.csv
└── notebooks/
    ├── 05-Data-Integration-Case-Study.ipynb   # notebook final, résultats et graphiques visibles
    └── case_study_outputs/                    # fichiers exportés par le notebook
        ├── store_summary.csv
        ├── category_summary.csv
        ├── reconciliation.csv
        ├── sales_review.csv
        ├── integration_review.csv
        ├── daily_revenue.csv
        ├── figure1_total_revenue_by_store.png
        ├── figure2_order_revenue_distribution.png
        ├── figure3_daily_revenue_by_store.png
        └── optional_category_mix_heatmap.png
```

---

## Instructions d'exécution

**1. Créer et activer un environnement virtuel** (Python 3.9 ou plus récent)

```bash
python3 -m venv .venv
source .venv/bin/activate
```

**2. Installer les dépendances** (`pandas`, `numpy`, `matplotlib`, `jupyter`)

```bash
python -m pip install -r requirements.txt
```

**3. Vérifier les données.** Les trois fichiers `case_*.csv` doivent être dans `data/`.

**4. Lancer le notebook** depuis le dossier `notebooks/`

```bash
cd notebooks
jupyter notebook
```

**5. Tout exécuter.** Ouvrir `05-Data-Integration-Case-Study.ipynb`, puis **Kernel → Restart & Run All**.

**6. Récupérer les résultats** dans `notebooks/case_study_outputs/`.

> Le notebook est reproductible : aucune valeur aléatoire, chemins relatifs, cellules exécutées dans l'ordre de haut en bas.

---

## Méthode en bref

| Étape | Ce que nous faisons | Résultat |
|:---|---|---|
| **1. Audit** | Effectifs, valeurs manquantes, doublons exacts, unicité des clés | Vue d'ensemble des trois sources |
| **2. Nettoyage** | Doublons exacts supprimés (avec comptage), identifiants normalisés, dates et nombres convertis (virgule décimale comprise) | `sales_valid`, `sales_review.csv` |
| **3. Jointures** | Left join avec `validate="many_to_one"` et indicateur, contrôle du nombre de lignes | `analysis`, `integration_review.csv`, `reconciliation.csv` |
| **4. Indicateurs** | Revenu = quantité × prix unitaire ; total, moyenne et médiane par magasin ; résumé par catégorie ; revenu quotidien | `store_summary.csv`, `category_summary.csv` |
| **5. Figures** | Total par magasin, distribution des commandes, évolution quotidienne | Trois PNG interprétés |
| **6. Conclusion** | Réponse au responsable, limites et recommandation | Note de synthèse |

**Règles de qualité appliquées**

- Aucune valeur n'est inventée : les lignes invalides sont gardées à part avec leurs raisons.
- Les commandes inhabituelles mais valides sont conservées.
- Les fichiers bruts ne sont jamais modifiés.
- Une commande sans magasin ou produit connu ne vaut pas zéro euro : elle est mise en revue.

---

## Contributions

| Membre | Contribution principale |
|:---|---|
| **Malik** | Audit des sources et nettoyage des données (sections 1 et 2) : doublons, normalisation, `sales_valid` / `sales_review` |
| **Jeremy** | Jointures, contrôles des effectifs et réconciliation (section 3) : `integration_review`, `analysis`, `reconciliation.csv` |
| **Aylin** | Indicateurs et tableaux de synthèse (section 4) : `store_summary`, `category_summary`, tableau quotidien ; Figure 1 |
| **Hiba** | Figures 2 et 3 et leurs interprétations (section 5) ; figure optionnelle sur le mix de produits |
| **Tous** | Relecture croisée de l'ensemble, note de synthèse (section 6), exports et vérification de la reproductibilité (section 7), README |

Le travail a été réparti en deux binômes (Malik et Jeremy pour les sections 1 à 3, Aylin et Hiba pour les sections 4 et 5), puis l'ensemble a été relu et validé par les quatre membres. Chaque membre peut expliquer l'unité d'observation, les choix de nettoyage, les contrôles de jointure, les calculs et chaque graphique.

---

## Limites à retenir

- Les données sont un extrait de commandes terminées, pas une trace complète de l'activité : un jour absent n'est pas un jour sans vente.
- Le revenu n'est pas le bénéfice : coûts, personnel, horaires et fréquentation sont inconnus.
- Aucune conclusion causale n'est tirée de cet échantillon.
