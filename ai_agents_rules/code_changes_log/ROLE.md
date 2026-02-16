# Code Changes Log - Regles de Tracabilite

## Fonction

Ce dossier centralise l'historique de toutes les modifications apportees au code du projet.

## Organisation

- **Un fichier par demande utilisateur**, nomme selon le format : `YYYY-MM-DD_description-courte.md`
- Chaque fichier utilise le template `_template.md`.
- Les fichiers sont classes chronologiquement.

## Regles

1. **Obligation de documentation** : Toute modification du code doit etre accompagnee d'une entree dans ce dossier.
2. **Exhaustivite** : Chaque intervention doit etre documentee, meme les corrections mineures.
3. **Validation utilisateur** : Le statut par defaut est "En attente de validation". Seul l'utilisateur peut passer le statut a "Valide".
4. **Immutabilite** : Les entrees existantes ne doivent pas etre supprimees. En cas d'erreur, ajouter une correction plutot que de modifier l'entree originale.
5. **Un agent = une section** : Si plusieurs agents interviennent sur la meme demande, chacun ajoute sa propre section dans le fichier.
