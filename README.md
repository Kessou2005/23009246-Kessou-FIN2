# Projet F16 : la loi d'Okun aux États-Unis

**Étudiant :** Kessou · **Code Apogée :** 23009246 · **Groupe :** FIN2 · **Module :** BD & DS, S7 FIN et CI (ENCG Settat)
**Dépôt :** `23009246-Kessou-FIN2`

## Question
La croissance trimestrielle du PIB réel américain permet-elle d'estimer la variation trimestrielle du taux de chômage ?
Algorithme principal : régression linéaire simple (algorithme 1), comparée à deux références naïves (moyenne du train, dernière valeur) et au Ridge.

## Données
- FRED (Federal Reserve Bank of St. Louis) : UNRATE (chômage mensuel, BLS) et GDPC1 (PIB réel trimestriel, BEA).
- Date d'extraction : 17 novembre 2026. Détails et licence : `data/raw/LISEZMOI.md`.
- Période utilisée : 1948 T2 à 2026 T3 (312 trimestres). Le mois d'octobre 2025 manque dans UNRATE : 2025 T4 et 2026 T1 sont exclus.

## Résultats (test chronologique 2010-2026, 65 trimestres)
| Méthode | MAE | RMSE | R² |
|---|---|---|---|
| Moyenne du train | 0,425 | 1,302 | −0,008 |
| Dernière valeur | 0,545 | 2,031 | −1,452 |
| **Régression linéaire** | **0,404** | **0,949** | **0,465** |

Pente = −0,291 (IC 95 % : −0,326 à −0,256). Sans 2020 T2 et T3, la régression devient la moins bonne : le résultat n'est pas robuste.

## Exécuter
1. Ouvrir `notebooks/projet_F16.ipynb` dans Google Colab ou Jupyter.
2. `pip install -r requirements.txt`, puis « Tout exécuter » (graine fixée à 42, données téléchargées depuis FRED).

## Contenu du dépôt
`notebooks/` notebook exécuté · `rapport/rapport.pdf` export du notebook · `presentation/` 6 diapositives (PDF + PPTX) · `figures/` graphiques · `video/` ou lien ci-dessous · `docs/` fiche du sujet · `DECLARATION_IA.md`

## Vidéo
Lien : *(à compléter si la vidéo n'est pas dans `video/demonstration.mp4`)*
