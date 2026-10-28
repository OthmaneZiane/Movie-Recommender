# 🎬 CinéReco — Système de recommandation de films

> Projet académique réalisé en **binôme** sur 8 semaines.  
> Combinaison de **Machine Learning** (recommandation content-based + filtrage collaboratif) et de **Business Intelligence** (tableau de bord Power BI).

## 📌 Présentation
Submergé par le choix, l'utilisateur peine à trouver un film qu'il aimera. **CinéReco** propose des films pertinents à partir de ses goûts et d'un jeu de données réel (**MovieLens 100K**).

## 🎯 Objectifs
- Recommandeur **content-based** (par genre / similarité)
- Recommandeur par **filtrage collaboratif** (SVD)
- **Évaluation** des modèles (RMSE, Precision@K, Recall@K)
- **Tableau de bord BI** (Power BI Desktop)
- **Application web** déployée (Streamlit Cloud)

## 🧱 Structure du projet
```
movie-recommender/
├── data/            # données (raw + traitées)
├── notebooks/       # exploration (EDA) & modélisation
├── src/             # code Python propre
├── app/             # application Streamlit
├── reports/         # rapport final + captures du dashboard
├── docs/            # cahier des charges
├── requirements.txt
└── README.md
```

## 🛠️ Installation
```bash
python -m venv venv
venv\Scripts\activate        # Windows
pip install -r requirements.txt
```

## 🚀 Utilisation
```bash
streamlit run app/app.py
```

## 📅 Planning (8 semaines)
| Sem. | Objectif |
|------|----------|
| 1 | Contexte, dataset, dépôt GitHub, cahier des charges |
| 2 | Exploration & nettoyage des données |
| 3 | Tableau de bord BI (Power BI) |
| 4 | Recommandeur baseline (popularité + content-based) |
| 5 | Filtrage collaboratif (SVD) |
| 6 | Évaluation & comparaison des modèles |
| 7 | Déploiement (Streamlit Cloud) |
| 8 | Documentation, rapport, présentation |

## 🧰 Technologies
Python · pandas · numpy · scikit-learn · scikit-surprise · Streamlit · Power BI · Git / GitHub

## 📚 Données
MovieLens 100K — <https://grouplens.org/datasets/movielens/100k-version/>

## 👥 Auteurs
ZIANE Othmane & HASKA Aymane — Projet académique

---
*Suivi de version : v0.1 — document de travail.*
