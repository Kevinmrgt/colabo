# Cursor - Regles Specifiques

## Identifiant agent
**Nom** : Cursor

## Contexte d'utilisation
Cursor intervient principalement pour :
- L'edition de code assistee par IA.
- Les modifications multi-fichiers coordonnees.
- La refactorisation guidee par le plan d'action.

## Regles specifiques

1. **Commandes explicites** : N'appliquer que les modifications explicitement demandees dans le plan.
2. **Mode review** : Toujours verifier le diff genere avant de l'appliquer.
3. **Contexte** : S'assurer que le contexte du projet est correctement charge avant toute modification.
4. **Tracabilite** : Toute modification effectuee via Cursor doit etre documentee dans `code_changes_log/`.
