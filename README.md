# Safe Data Schema Explorer 🔍

> Extraire la structure et les statistiques d'un dataset sans exposer de données sensibles — une bonne pratique essentielle pour tout Data Analyst travaillant avec des données confidentielles.

---

## 🎯 Objectif

Lorsqu'on travaille avec des datasets sensibles (banque, santé, assurance), partager des fichiers bruts avec des outils IA externes ou des collaborateurs représente un risque sérieux pour la confidentialité des données et peut violer le **RGPD**.

Ce notebook résout ce problème en extrayant **uniquement la structure** du dataset — noms de colonnes, types de données, statistiques agrégées et indicateurs de qualité — sans jamais exposer une seule valeur réelle.

**Ce que vous pouvez partager en toute sécurité :**
- Noms de colonnes et types de données
- Statistiques agrégées (min, max, moyenne, écart-type)
- Nombre de valeurs nulles et pourcentages
- Nombre de valeurs uniques
- Rapport de qualité des données

**Ce qui ne quitte jamais votre machine :**
- Les enregistrements individuels
- Les informations personnelles
- Les numéros de compte ou détails financiers
- Toute valeur permettant d'identifier une personne

---

## 📋 Prérequis

```bash
pip install pandas numpy
```

---

## 🚀 Comment utiliser

1. Cloner le repository
```bash
git clone https://github.com/your-username/safe-data-schema-explorer.git
cd safe-data-schema-explorer
```

2. Ouvrir le notebook
```bash
jupyter notebook schema_explorer.ipynb
```

3. Modifier le chemin du fichier dans la première cellule
```python
FICHIER = 'votre_fichier.csv'  # ← modifier ici
```

4. Exécuter toutes les cellules — 2 fichiers CSV sécurisés seront générés dans `/outputs`

---

## 📊 Fichiers générés

| Fichier | Contenu | Sécurisé à partager |
|---|---|---|
| `schema_export.csv` | Noms de colonnes, types, valeurs nulles, valeurs uniques | ✅ Oui |
| `stats_numeriques.csv` | Min, max, moyenne, écart-type, quartiles | ✅ Oui |

---

## 🗂️ Structure du Notebook

| Section | Description |
|---|---|
| 1. Dimensions | Nombre de lignes, colonnes, taille mémoire |
| 2. Schéma | Noms de colonnes, types, valeurs nulles, valeurs uniques |
| 3. Stats Numériques | Min, max, moyenne, écart-type, quartiles |
| 4. Stats Catégorielles | Valeurs les plus fréquentes, valeurs uniques |
| 5. Qualité des Données | Taux de complétude, doublons, colonnes problématiques |
| 6. Export | Génère 2 fichiers CSV sécurisés |

---

## 💡 Cas d'Usage Réel

Cet outil a été utilisé dans le cadre d'un projet de **Détection de Fraude Bancaire** impliquant 284 807 transactions. Plutôt que de partager le dataset brut avec un assistant IA, seuls le schéma et les statistiques ont été partagés — permettant une collaboration complète tout en gardant toutes les données financières sensibles privées.

Résultats du projet :
- Modèle : XGBoost
- AUC-ROC : 0.98
- Rappel : 97.56%
- Transactions analysées : 284 807
- Fraudes détectées : 480 / 492

---

## 📁 Structure du Projet

```
safe-data-schema-explorer/
│
├── README.md                    ← Vous êtes ici
├── schema_explorer.ipynb        ← Notebook principal
├── outputs/
│   ├── schema_export.csv        ← Exemple de sortie (colonnes & types)
│   └── stats_numeriques.csv     ← Exemple de sortie (statistiques)
└── .gitignore
```

---

## ⚖️ Confidentialité & RGPD

Cet outil a été conçu avec le principe de **protection des données dès la conception** (Privacy by Design). Il est particulièrement utile dans les secteurs réglementés tels que :

- 🏦 Banque & Finance
- 🏥 Santé
- 🛡️ Assurance
- 🏛️ Secteur Public

---

## 🤝 Contribuer

N'hésitez pas à ouvrir une issue ou soumettre une pull request pour améliorer cet outil — le support de formats supplémentaires (Excel, JSON, Parquet) est le bienvenu.

---

## 📄 Licence

Licence MIT — libre d'utilisation, de modification et de distribution.

---

*Construit dans le cadre d'un projet de Détection de Fraude Bancaire — [Voir le projet complet sur LinkedIn]www.linkedin.com/in/ryann-loic-bondeh-essomba-108ab6388*
