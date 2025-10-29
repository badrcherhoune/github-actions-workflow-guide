# Structure d’un fichier Workflow GitHub Actions (`ci.yml`)

Le fichier `ci.yml` (ou tout autre `.yml` sous `.github/workflows/`) décrit un **workflow GitHub Actions**.  
Il suit une structure logique à plusieurs niveaux :

workflow → on → jobs → steps → uses/run/env/if/...


---

## Exemple de structure commentée

```yaml
# Nom du workflow affiché dans GitHub Actions
name: Nom_du_workflow  

# Événements qui déclenchent l’exécution du workflow
on:
  # Exemple : push, pull_request, schedule, workflow_dispatch, etc.
  <déclencheurs>

# Variables d’environnement globales, accessibles à tous les jobs
env:
  <variables globales>

# Paramètres par défaut appliqués aux étapes (par ex. shell, working-directory)
defaults:
  <paramètres par défaut>

# Définition des différents jobs (tâches) du workflow
jobs:
  # Nom du job (ex. build, test, deploy)
  <nom_du_job>:
    # Options du job : environnement d’exécution, dépendances, conditions, etc.
    <options_du_job>

```
| Niveau                       | Description                                                                  |
| ---------------------------- | ---------------------------------------------------------------------------- |
| **workflow**                 | Point d’entrée principal du fichier (nom et structure globale).              |
| **on**                       | Définit les événements qui déclenchent le workflow (push, pull_request…).    |
| **env**                      | Variables d’environnement globales partagées entre les jobs.                 |
| **defaults**                 | Paramètres par défaut pour les étapes (comme le shell ou le répertoire).     |
| **jobs**                     | Contient un ou plusieurs jobs (parallèles ou séquentiels).                   |
| **steps**                    | Ensemble d’actions exécutées à l’intérieur d’un job.                         |
| **uses / run / env / if...** | Détails des étapes : actions, commandes, conditions, variables locales, etc. |
