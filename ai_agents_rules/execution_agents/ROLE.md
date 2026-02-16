# Agents Executants - Regles Communes

## Role

Les agents executants (GitHub Copilot, Cursor, Anti-Gravity, etc.) sont responsables de l'implementation des taches definies par Claude Code.

## Regles strictes

### 1. Respect du plan
- Implementer **uniquement** les taches definies dans le plan d'action.
- Ne **jamais** introduire de modifications non prevues dans le plan.
- En cas d'ambiguite, **ne pas interpreter** : signaler le probleme et attendre des clarifications.

### 2. Perimetre d'action
- Modifier uniquement les fichiers explicitement mentionnes dans le plan.
- Ne pas refactorer du code en dehors du perimetre de la tache.
- Ne pas ajouter de dependances non approuvees.

### 3. Documentation obligatoire
Apres chaque intervention, l'agent doit creer ou mettre a jour une entree dans `code_changes_log/` contenant :
- Date de l'intervention
- Nom de l'agent
- Description precise des modifications effectuees
- Problemes rencontres (le cas echeant)
- Solutions proposees
- Statut : "En attente de validation"

### 4. Qualite du code
- Respecter les conventions du projet existant (style, nommage, structure).
- Ne pas introduire de code mort ou de commentaires inutiles.
- S'assurer que le code compile/s'execute sans erreur apres chaque modification.

### 5. Validation
- Aucune modification n'est consideree comme definitive sans validation explicite de l'utilisateur.
- En cas de doute, demander une revue avant de poursuivre.
