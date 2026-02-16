# AI Agents Rules

Ce dossier centralise les regles, roles et processus de collaboration entre les differents agents IA du projet.

## Structure

```
ai_agents_rules/
├── README.md                  # Ce fichier
├── project_context/           # Projet utilisateur - Source de verite
│   └── ROLE.md                # Regles et contenu attendu
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

1. L'utilisateur soumet une demande.
2. Les agents consultent **project_context/** pour comprendre le projet.
3. **Claude Code** analyse le projet et produit un plan d'action detaille.
3. Le plan est transmis aux **agents executants** pour implementation.
4. Chaque modification est enregistree dans **code_changes_log/**.
5. L'utilisateur valide ou demande des corrections.
