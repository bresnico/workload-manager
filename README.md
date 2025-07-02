# Workload Manager Dashboard

Un tableau de bord interactif pour le suivi et la visualisation de la charge de travail par domaine d'activité.

## Description

Ce projet propose un dashboard Quarto Shiny permettant de visualiser et analyser la répartition des heures de travail par domaine d'activité. Le dashboard se connecte à une Google Sheet pour récupérer les données en temps réel et offre des visualisations interactives pour le suivi de la charge de travail.

## Fonctionnalités

- **Visualisation interactive** : Graphiques dynamiques avec Plotly
- **Filtrage avancé** : Filtres par domaine et par période
- **Tableaux de bord** : Métriques clés et résumés visuels
- **Source de données flexible** : Connexion Google Sheets avec fallback sur données locales
- **Interface responsive** : Dashboard adaptatif utilisant Bootstrap

## Structure du projet

```
workload_manager/
├── dashboard.qmd          # Code source principal du dashboard
├── dashboard.html         # Version compilée du dashboard
├── planification.csv      # Données de planification locale
├── test_sheet.R          # Scripts de test
└── dashboard_files/      # Assets générés par Quarto
```

## Prérequis

- R (version 4.0+)
- Quarto
- Packages R requis :
  - shiny
  - dplyr
  - ggplot2
  - plotly
  - DT
  - googlesheets4
  - tidyr
  - bslib
  - bsicons

## Installation

1. Clonez le dépôt :
```bash
git clone https://github.com/votre-username/workload_manager.git
cd workload_manager
```

2. Installez les dépendances R :
```r
install.packages(c("shiny", "dplyr", "ggplot2", "plotly", "DT", 
                   "googlesheets4", "tidyr", "bslib", "bsicons"))
```

## Utilisation

### Lancement du dashboard

```bash
quarto serve dashboard.qmd
```

Le dashboard sera accessible à l'adresse : `http://localhost:XXXX`

### Configuration des données

1. **Google Sheets** : Le dashboard se connecte par défaut à une Google Sheet. Modifiez l'URL dans le fichier `dashboard.qmd` (ligne 27).

2. **Données locales** : Créez ou modifiez le fichier `planification.csv` avec vos données de planification :
```csv
domaine,planification
"Domaine 1",100
"Domaine 2",150
```

## Fonctionnalités du dashboard

- **Sidebar** : Filtres pour sélectionner les domaines et périodes
- **Visualisations** :
  - Graphique en barres des heures par domaine
  - Évolution temporelle des heures
- **Métriques** :
  - Total des heures (réalisé vs planifié)
  - Nombre de domaines
  - Moyenne par entrée
- **Tableau détaillé** : Vue tabulaire des données avec pagination

## Déploiement

Le dashboard peut être déployé sur diverses plateformes :
- Serveur Shiny
- ShinyApps.io
- Connect
- Serveur web classique (version statique)

## Licence

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.

## Contribution

Les contributions sont les bienvenues ! N'hésitez pas à ouvrir une issue ou proposer une pull request.