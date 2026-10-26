# Modele manuel ou modele AutoML ? (TP05)

| Critere | Manuel (rf 500/16) | AutoML (FLAML 90 s) |
|---|---|---|
| Famille de modele | Foret aleatoire (RandomForest) | XGBoost (XGBClassifier) |
| F1 sur le jeu de test | 0.8669 | 0.8582 |
| Temps de recherche machine | 10 s | 90 s |
| Temps humain (estimation) | 30 min | 2 min |
| Latence mediane (ms) | 15 ms | ~20 ms |
| Latence p95 (ms) | 25 ms | 40 ms |
| Taille du fichier (Mo) | **13.37 Mo** | **0.28 Mo** |
| Explicabilite | Bonne (importances, arbres) | Moyenne (importances, structure complexe) |

## Decision (5 lignes)
Je choisirais le modele **manuel (RandomForest)** en production pour les raisons suivantes :
1. Il offre un F1 legerement superieur (0.8669 vs 0.8582) sur ce jeu de test.
2. Sa latence est tres bonne pour un service HTTP local.
3. Sa taille plus importante (13.37 Mo) reste acceptable pour un serveur.
4. Son explicabilite est meilleure, ce qui est un atout majeur dans le secteur bancaire (reglementation).
5. L'AutoML reste excellent pour prototyper rapidement, mais le modele manuel est plus sur pour un deploiement final.