# 🎧 Dashboard Hits Spotify

Dashboard **Streamlit** d'aide à la décision pour le directeur artistique d'un label indépendant : quels titres sortir en single pour maximiser les chances de hit ?

**👉 [Voir l'application en ligne](https://dashboardstspotify-qrjlk7k9vchcvxhjr6xdzn.streamlit.app/)**

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-1.36+-FF4B4B?logo=streamlit&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-5.20+-3F4F75?logo=plotly&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-2.0+-150458?logo=pandas&logoColor=white)

## 💡 Message clé

> **Un hit Spotify se chante et dure moins de 4 minutes.**

- 70 % des hits (popularité ≥ 70) durent entre 2,5 et 4 minutes ; au-delà de 5 minutes, le taux de hits tombe à 5,3 % (contre 10,6 % pour le format court)
- Un titre instrumental a 9 fois moins de chances d'être un hit (1,1 % contre 10,1 %)
- La durée moyenne des sorties est passée de 4 min 14 s (2000) à 3 min 14 s (2020)

## 📊 Fonctionnalités

| Page | Contenu |
|---|---|
| **Synthèse** | Le message clé et 3 KPIs actionnables : taux de hits, taux de hits des titres de 2,5 à 4 min, taux de hits des instrumentaux |
| **Détail** | Une visualisation par onglet : durée dans le temps, chanté vs instrumental, profil sonore, popularité par genre |
| **Tester un single** | L'utilisateur décrit son titre (genre, durée, voix) et obtient le taux de hits des titres similaires |

Filtres communs dans la barre latérale : genre, période de sortie, seuil de hit.

## 🗂️ Données

[Spotify Songs](https://github.com/rfordatascience/tidytuesday/tree/master/data/2020/2020-01-21) (TidyTuesday, janvier 2020) : 32 833 lignes, soit **28 356 titres uniques** après dédoublonnage, 23 variables (popularité, genre, date de sortie, durée, indices audio).

## 🚀 Lancer en local

```bash
pip install -r requirements.txt
streamlit run Synthèse.py
```

## 📂 Structure

```
Synthèse.py                     # page d'accueil : message + KPIs
pages/1_🔎_Détail.py             # un onglet par visualisation
pages/2_🎯_Tester_un_single.py   # outil d'aide au choix d'un single
utils.py                        # chargement (@st.cache_data), filtres, formats
cadrage.md                      # document de cadrage (message, audience, KPIs)
data/spotify_songs.csv
```

📄 Le **[document de cadrage](cadrage.md)** explique le choix du message, de l'audience et des KPIs.
