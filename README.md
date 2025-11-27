# 🏙️ App_Dans_ma_rue – Analyse des signalements citoyens à Paris (Power BI)

Ce dépôt contient une application **Power BI** construite à partir des signalements de l’application « Dans Ma Rue » de la Ville de Paris.  
Objectif : **analyser, cartographier et suivre les anomalies signalées dans l’espace public parisien** (propreté, mobilier urbain, objets abandonnés, etc.) pour mieux comprendre les enjeux de qualité de vie et de gestion urbaine.

---

## 📊 Aperçu du projet

- **Type de projet** : Data Visualisation / Business Intelligence  
- **Outil principal** : Power BI Desktop  
- **Données** : fichier CSV `dans-ma-rue-2025.csv` (~225 000 signalements en 2025)  
- **Livrable clé** : rapport interactif `Dans_ma_rue.pbix`  

Ce rapport permet à un décideur (ville, bailleur, association de quartier, etc.) de répondre à des questions comme :

- Quels types d’anomalies sont les plus fréquents dans Paris en 2025 ?
- Quels arrondissements et quartiers sont les plus concernés ?
- Comment évoluent les signalements au fil des mois ?
- Quels canaux d’entrée (application, web…) sont les plus utilisés ?
- Quel volume de travail est généré pour les équipes d’intervention ?

---

## 🧾 Données utilisées

Fichier principal : `dans-ma-rue-2025.csv`  

- **Nombre de lignes** : ~225 000 signalements  
- **Période couverte** : année 2025  
- **Zone géographique** : Ville de Paris (arrondissements, conseils de quartier)

### Principales variables

| Colonne                | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| `ID DECLARATION`       | Identifiant unique du signalement                                           |
| `TYPE DECLARATION`     | Grande catégorie d’anomalie (Propreté, Mobiliers urbains, Objets abandonnés…) |
| `SOUS TYPE DECLARATION`| Détail du type (mégots, déchets, mobilier détérioré, etc.)                  |
| `ADRESSE`              | Adresse textuelle du signalement                                            |
| `CODE POSTAL`          | Code postal (généralement 75001–75020)                                      |
| `VILLE`                | Arrondissement textuel (Paris 1, Paris 13, etc.)                            |
| `ARRONDISSEMENT`       | Numéro d’arrondissement (1 à 20)                                           |
| `CONSEIL DE QUARTIER`  | Conseil de quartier concerné (zone infra-arrondissement)                    |
| `DATE DECLARATION`     | Date et heure du signalement                                               |
| `ANNEE DECLARATION`    | Année (ici 2025)                                                            |
| `MOIS DECLARATION`     | Mois du signalement (1–12)                                                  |
| `OUTIL SOURCE`         | Canal d’entrée (application mobile, web, etc.)                              |
| `INTERVENANT`          | Type d’équipe ou service en charge du traitement                            |
| `ID_DMR`               | Identifiant interne « Dans Ma Rue »                                         |
| `geo_shape`            | Géométrie (format JSON)                                                     |
| `geo_point_2d`         | Coordonnées latitude/longitude                                              |
| `mois_annee_decla`     | Clé temps (AAAAMM) pour les analyses mensuelles                             |

> ⚠️ Les données brutes ne sont pas modifiées dans le dépôt. Le nettoyage et la modélisation sont réalisés dans Power BI.

---

## 🧠 Objectifs d’analyse

1. **Suivi global des signalements**
   - Volumes mensuels
   - Répartition par type et sous-type d’anomalie

2. **Analyse territoriale**
   - Comparaison des arrondissements
   - Zoom par conseil de quartier
   - Cartographie des points chauds (hotspots)

3. **Compréhension opérationnelle**
   - Répartition par intervenant
   - Analyse des canaux d’entrée (`OUTIL SOURCE`)
   - Identification des zones à prioriser pour les équipes terrain

4. **Support à la décision**
   - Aide à la planification des tournées
   - Identification des quartiers « sensibles »
   - Suivi de la qualité de l’espace public perçue par les habitants

---

## 📈 Fonctionnalités du rapport Power BI

Le fichier `Dans_ma_rue.pbix` est organisé en plusieurs pages thématiques (onglets) :

1. **Vue d’ensemble**
   - KPIs clés (nombre total de signalements, nb de types différents, etc.)
   - Chronologie des signalements (par mois)
   - Top 5 des types d’anomalies

2. **Analyse par type d’anomalie**
   - Diagramme des `TYPE DECLARATION` et `SOUS TYPE DECLARATION`
   - Filtrage dynamique par période / arrondissement

3. **Cartographie**
   - Carte interactive des signalements (basée sur `geo_point_2d`)
   - Vue par arrondissement et/ou conseil de quartier
   - Possibilité de filtrer par type de problème

4. **Canaux & intervenants**
   - Répartition des signalements par `OUTIL SOURCE`
   - Analyse du volume par `INTERVENANT`

5. **Exploration détaillée**
   - Table de détails (drill-through) par signalement
   - Recherche d’adresses / types spécifiques

---

## 📁 Structure du dépôt

```text
App_Dans_ma_rue/
├── README.md                     # Ce document
├── Dans_ma_rue.pbix              # Rapport Power BI complet
├── dans-ma-rue-2025.csv          # Données brutes (signalements 2025)
└── .gitignore / licence / etc.   # Fichiers de configuration GitHub
