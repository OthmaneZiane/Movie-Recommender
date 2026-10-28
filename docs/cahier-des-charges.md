# CinéReco — Système de recommandation de films
### Cahier des charges

| | |
|---|---|
| **Auteurs** | ZIANE Othmane & HASKA Aymen — projet réalisé en binôme |
| **Client / évaluateur** | Professeur Mme.OUNACER SOUMIA (projet académique) |
| **Date** | 28 octobre 2026 |
| **Version** | v0.1 — brouillon à valider |
| **Durée** | 8 semaines |

---

## 1. Contexte
Aujourd'hui, un utilisateur est submergé par le nombre de films disponibles (VOD, streaming) et peine à choisir quelque chose qu'il aimera vraiment. Ce projet a pour but de concevoir un **système de recommandation de films** qui propose, à partir des goûts de l'utilisateur et de données existantes, des films susceptibles de lui plaire.

Le projet s'inscrit dans un cadre académique d'une durée de **8 semaines**, réalisé en **binôme**. Il doit mobiliser au moins deux des thèmes suivants : **IA / ML / BI / Jeu de données**. Notre solution combine **Machine Learning (ML)** et **Business Intelligence (BI)** autour d'un **jeu de données réel**.

## 2. Problème à résoudre
> « Comment aider un utilisateur à découvrir rapidement des films qu'il va aimer, sans parcourir des centaines de titres ? »

## 3. Objectifs (SMART)
- **Spécifique** : développer un recommandeur combinant une approche *content-based* et une approche *filtrage collaboratif*, plus un tableau de bord BI.
- **Mesurable** : atteindre un **RMSE < 0.95** sur le jeu MovieLens 100K ; proposer **≥ 10 recommandations** par requête ; dashboard avec **≥ 4 indicateurs**.
- **Atteignable** : jeu de données public et propre, bibliothèques Python éprouvées, déploiement gratuit (Streamlit Cloud).
- **Réaliste** : périmètre limité à un jeu de données existant (pas de collecte de données).
- **Temporel** : livrable complet en 8 semaines.

## 4. Périmètre
**Inclus :**
- Exploration et nettoyage des données.
- Recommandeur *content-based* (par genre / similarité).
- Recommandeur par *filtrage collaboratif*.
- Comparaison et évaluation des modèles.
- Tableau de bord BI (statistiques, top films, genres) réalisé avec **Power BI Desktop**.
- Application web déployée gratuitement.
- Documentation et dépôt GitHub.

**Exclu :**
- Collecte de nouvelles données / création d'un vrai compte utilisateurs.
- Recommandations en temps réel sur des millions d'articles.
- Application mobile.

## 5. Parties prenantes
| Partie prenante | Rôle | Besoin |
|---|---|---|
| Professeur | Client / évaluateur | Respect du sujet, qualité, traçabilité, compréhension |
| Utilisateur final | Bénéficiaire | Recommandations pertinentes, interface simple |
| Étudiants (binôme) | Développeurs | Livrer dans les temps, apprendre |

## 6. Exigences fonctionnelles
Format : *histoire utilisateur* + priorité **MoSCoW** (Must / Should / Could / Won't have).

| ID | Histoire utilisateur | Priorité |
|---|---|---|
| F1 | En tant qu'utilisateur, je saisis mes films préférés pour recevoir des recommandations | **Must** |
| F2 | En tant qu'utilisateur, je reçois des films similaires à ceux que j'aime (content-based) | **Must** |
| F3 | En tant qu'utilisateur, je comprends pourquoi ce film m'est proposé | Should |
| F4 | En tant qu'utilisateur, je découvre des films aimés par des gens de même goût (collaboratif) | Should |
| F5 | En tant qu'utilisateur, je peux chercher un film précis | Could |
| F6 | En tant qu'analyste, je consulte un tableau de bord avec top films, notes et genres | **Must** |

## 7. Exigences non-fonctionnelles
| ID | Exigence | Priorité |
|---|---|---|
| NF1 | L'application affiche une réponse en **< 3 secondes** | **Must** |
| NF2 | L'application fonctionne sur tout navigateur | **Must** |
| NF3 | Le code est commenté et respecte les conventions Python (PEP 8) | Should |
| NF4 | Le projet est **reproductible** (requirements.txt + README) | **Must** |
| NF5 | Les modèles sont **évalués** (RMSE, Precision@K, Recall@K) | **Must** |

## 8. Solution technique
- **Langage** : Python
- **Données** : MovieLens 100K (Open Source, GroupLens)
- **Traitement** : pandas, numpy
- **Modèles** : scikit-learn (content-based), Surprise (filtrage collaboratif, SVD)
- **Évaluation** : scikit-learn / Surprise
- **Visualisation / BI** : **Power BI Desktop** (gratuit) pour le tableau de bord livré au professeur (.pbix + captures) ; matplotlib / seaborn pour les graphiques du rapport
- **Interface & déploiement** : Streamlit + Streamlit Cloud (gratuit)
- **Versioning** : Git + GitHub (commits réguliers, Project board)

### Architecture (schéma)
```
[MovieLens data] → [Preprocessing] → [Modèles ML] → [API Streamlit] → [Utilisateur]
                        ↓
                  [Dashboard Power BI]
```

## 9. Livrables
- Dépôt GitHub public (traçabilité).
- Application web déployée (lien public).
- Tableau de bord BI (Power BI Desktop : fichier `.pbix` + captures d'écran / vidéo).
- Rapport final (PDF).
- Présentation (slides).
- Cahier des charges (ce document).

## 10. Planning (8 semaines)
| Semaine | Objectif | Livrable |
|---|---|---|
| 1 | Contexte, dataset, dépôt GitHub, cahier des charges | Repo + CDC |
| 2 | Exploration & nettoyage des données | Notebook EDA |
| 3 | Tableau de bord BI (Power BI) | Dashboard |
| 4 | Recommandeur baseline (popularité + content-based) | Module ML |
| 5 | Filtrage collaboratif (SVD / Surprise) | Module ML avancé |
| 6 | Évaluation et comparaison des modèles | Rapport d'évaluation |
| 7 | Déploiement (Streamlit Cloud) | App en ligne |
| 8 | Documentation, rapport, présentation | Rapport + slides |

## 11. Risques et parades
| Risque | Parade |
|---|---|
| Bloqué sur un concept | Tutoriels, documentation, demande d'aide précoce |
| Filtrage collaboratif trop complexe | Le content-based est un « Must » fonctionnel seul ; le collaboratif = « Should » |
| Déploiement qui échoue | Streamlit Cloud très simple ; sinon fournir captures + vidéo |
| Partage en ligne de Power BI (licence payante) | Livrer le `.pbix` + captures / vidéo dans le rapport (100% gratuit) |
| Manque de temps | MoSCoW : finir d'abord les « Must » |

## 12. Critères d'acceptation
- [ ] Application déployée et accessible via un lien public.
- [ ] Dépôt GitHub public avec README, requirements.txt et commits réguliers.
- [ ] Au moins **2 approches** de recommandation comparées et évaluées (métriques).
- [ ] Tableau de bord BI présent.
- [ ] Cahier des charges, rapport et présentation livrés.

---

*Document de travail v0.1 — à valider avec le professeur.*
