# Project Context - Projet Utilisateur

## Fonction

Ce dossier contient les informations relatives au projet de l'utilisateur. Il sert de reference unique pour tous les agents IA afin de comprendre le projet avant toute intervention.

## Configuration du projet

Le fichier `project_config.yaml` permet de referencer un projet situe n'importe ou sur le systeme de fichiers.

### Champs du fichier de configuration

| Champ | Obligatoire | Description |
|-------|-------------|-------------|
| `project_path` | Oui | Chemin absolu vers le dossier racine du projet |
| `project_name` | Oui | Nom du projet |
| `description` | Oui | Description courte du projet |
| `tech_stack` | Non | Liste des technologies utilisees |
| `entry_points` | Non | Fichiers/dossiers cles a analyser en priorite (chemins relatifs depuis `project_path`) |
| `exclude` | Non | Patterns de fichiers/dossiers a ignorer lors de l'analyse |

### Exemple

```yaml
project_path: "C:\\Users\\Kevin\\Projects\\mon-app"
project_name: "Mon App"
description: "Application web de gestion de taches"
tech_stack:
  - Next.js
  - TypeScript
  - PostgreSQL
entry_points:
  - src/
  - package.json
exclude:
  - node_modules/
  - .git/
  - dist/
```

## Contenu attendu (optionnel)

En plus du fichier de configuration, l'utilisateur peut ajouter des documents dans ce dossier :

### 1. Description du projet
- Objectif general du projet
- Public cible
- Fonctionnalites principales

### 2. Architecture technique
- Stack technique (langages, frameworks, base de donnees, etc.)
- Structure des dossiers du projet
- Diagrammes d'architecture (le cas echeant)

### 3. Contraintes et exigences
- Contraintes techniques (versions, compatibilite, performance)
- Exigences fonctionnelles
- Exigences non fonctionnelles (securite, accessibilite, SEO, etc.)

### 4. Configuration et environnement
- Variables d'environnement necessaires
- Instructions de setup local
- Dependances externes (API tierces, services cloud, etc.)

## Regles

1. **Source de verite** : Ce dossier est la reference principale pour comprendre le projet.
2. **Lecture obligatoire** : Tout agent doit lire `project_config.yaml` avant de commencer une analyse ou une intervention.
3. **Mise a jour** : Les informations doivent etre mises a jour a chaque evolution significative du projet.
4. **Propriete utilisateur** : Seul l'utilisateur peut modifier le contenu de ce dossier. Les agents peuvent proposer des mises a jour mais ne les appliquent pas directement.
