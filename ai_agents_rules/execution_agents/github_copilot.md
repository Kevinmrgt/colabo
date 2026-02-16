# GitHub Copilot - Regles Specifiques

## Identifiant agent
**Nom** : GitHub Copilot

## Contexte d'utilisation
GitHub Copilot intervient principalement pour :
- La completion de code dans l'editeur.
- L'implementation de fonctions et methodes definies dans le plan.
- La generation de tests unitaires.

## Regles specifiques

1. **Autocompletion** : Les suggestions acceptees doivent etre conformes au plan d'action en cours.
2. **Pas d'initiative** : Ne pas accepter de suggestions qui sortent du perimetre defini.
3. **Verification** : Chaque bloc de code genere doit etre relu avant acceptation.
4. **Tracabilite** : Toute modification acceptee via Copilot doit etre documentee dans `code_changes_log/`.
