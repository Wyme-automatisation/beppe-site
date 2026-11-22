# Kit de passation — site beppe.fr

Ce dossier contient tout ce qu'il faut pour que Claude Code construise le site v1 :

- `CLAUDE.md` : le cahier des charges. Claude Code le lit automatiquement à chaque session.
- `PREMIER-MESSAGE.md` : le premier message à lui envoyer.
- `maquette-v1/` : les maquettes des 5 pages, du menu, du pied de page, de la charte et du personnage.

## Étapes

1. **Préparer** : installer Node.js (version LTS) et Claude Code, créer un compte GitHub.
2. **Créer le dossier** `beppe-site` sur ton ordinateur, y copier le contenu de ce kit, ouvrir un terminal dans ce dossier et lancer `claude`.
3. **Construire** : envoyer le premier message, valider la structure, puis avancer page par page en regardant le résultat en local.
4. **Versionner** : demander à Claude Code d'initialiser Git et de pousser le projet sur un dépôt GitHub privé.
5. **Héberger** : connecter le dépôt GitHub à l'hébergeur choisi ; chaque modification poussée met le site à jour.
6. **Brancher le domaine** : chez le registrar de beppe.fr, faire pointer le domaine vers l'hébergeur (l'hébergeur indique les réglages DNS).
7. **Brancher le formulaire** : créer un workflow n8n avec un webhook (enregistrement du contact dans le CRM + e-mail d'alerte), puis mettre son URL dans la variable `PUBLIC_FORM_ENDPOINT` chez l'hébergeur.
8. **Avant la mise en ligne** : compléter les mentions légales (validation par l'expert-comptable ou un juriste), remplacer les [champs à compléter], vérifier le site sur téléphone.
