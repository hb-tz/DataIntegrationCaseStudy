# Data Integration Case Study

M1-INF4 · Atelier Python pour Data Science · Séance 5

**Groupe 09 :** Malik Louni, Jérémy Vidocin, Aylin Danistekin, Hiba Tazi

## Sujet

Campus Tech est un revendeur fictif de matériel informatique. Le responsable pense que le magasin qui a le plus gros chiffre d'affaires est le meilleur et qu'il faut copier son approche partout. On a nettoyé et relié trois fichiers (commandes, magasins, produits) pour vérifier cette affirmation sur la période du 1er au 28 avril 2025. Les données sont fictives.

## Contenu du dépôt

```
data/                                  données fournies (non modifiées)
    case_sales.csv
    case_stores.csv
    case_products.csv
notebooks/
    05-Data-Integration-Case-Study.ipynb   notebook final, avec les résultats
    case_study_outputs/                    tableaux CSV et figures PNG exportés
requirements.txt
```

## Exécution

Avec Python 3.9 ou plus récent :

```bash
python -m venv .venv
.venv\Scripts\activate          # Windows
source .venv/bin/activate       # macOS / Linux
pip install -r requirements.txt
```

Ensuite, lancer `jupyter notebook` dans le dossier `notebooks/`, ouvrir `05-Data-Integration-Case-Study.ipynb` et faire **Kernel → Restart & Run All**. Le notebook lit les données dans `../data/` et écrit les tableaux et les figures dans `notebooks/case_study_outputs/`.

## Contributions

| Membre | Partie |
|:---|---|
| Malik Louni | Audit des sources et nettoyage (sections 1 et 2) |
| Jérémy Vidocin | Jointures, contrôle des effectifs et réconciliation (section 3) |
| Aylin Danistekin | Indicateurs, tableaux de synthèse et figure 1 (section 4) |
| Hiba Tazi | Figures 2 et 3, interprétations et figure optionnelle (section 5) |

On a travaillé en deux binômes (Malik et Jérémy sur les sections 1 à 3, Aylin et Hiba sur les sections 4 et 5). La note de synthèse, les exports, le README et la relecture finale ont été faits ensemble.

## Résultat principal

Paris Est a le plus gros chiffre d'affaires total, mais Lille Centre a le montant moyen par commande le plus élevé. Le plus gros total ne suffit donc pas à désigner le meilleur magasin. L'extrait est incomplet (tous les jours ne sont pas présents) et on ne connaît que le chiffre d'affaires, pas le bénéfice.
