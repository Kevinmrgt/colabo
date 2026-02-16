# AI Agents Rules

Ce dossier centralise les regles, roles et processus de collaboration entre les differents agents IA du projet.

## Structure

```
ai_agents_rules/
├── README.md                  # Ce fichier
├── project_context/           # Projet utilisateur - Source de verite
│   ├── ROLE.md                # Regles et contenu attendu
│   └── project_config.yaml    # Configuration du projet (chemin, stack, etc.)
├── claude_code/               # Agent principal - Analyse et planification
│   ├── ROLE.md                # Definition du role de Claude Code
│   └── plan_template.md       # Template pour les plans d'action
├── execution_agents/          # Agents executants
│   ├── ROLE.md                # Definition du role des agents executants
│   ├── github_copilot.md      # Regles specifiques a GitHub Copilot
│   ├── cursor.md              # Regles specifiques a Cursor
│   └── anti_gravity.md        # Regles specifiques a Anti-Gravity
└── code_changes_log/          # Suivi des modifications
    ├── ROLE.md                # Regles de tracabilite
    └── _template.md           # Template pour chaque demande utilisateur
```

## Contraintes generales

1. **Documentation** : Chaque agent doit documenter ses actions avec rigueur.
2. **Tracabilite** : Aucune modification ne doit etre appliquee sans tracabilite.
3. **Validation** : Une resolution n'est consideree comme definitive qu'apres validation explicite de l'utilisateur.
4. **Clarte** : La clarte, la maintenabilite et la verifiabilite sont prioritaires.

## Flux de travail

1. L'utilisateur configure `project_context/project_config.yaml` avec le chemin de son projet.
2. L'utilisateur soumet une demande.
3. Les agents lisent `project_config.yaml` pour localiser et comprendre le projet.
4. **Claude Code** analyse le projet et produit un plan d'action detaille.
5. Le plan est transmis aux **agents executants** pour implementation.
6. Chaque modification est enregistree dans **code_changes_log/**.
7. L'utilisateur valide ou demande des corrections.
