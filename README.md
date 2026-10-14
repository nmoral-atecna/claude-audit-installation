# outils-dev

Marketplace de plugins Claude Code.

## Installation

```
/plugin marketplace add <url-git-de-ce-dépôt>
/plugin install onboarding@outils-dev
```

Pour un dépôt GitLab, passer l'URL complète (`https://gitlab.exemple.com/groupe/outils-dev.git`). Ajouter `#<branche-ou-tag>` pour épingler une version.

## Plugins

### onboarding

`/onboarding:check-install [ref]` audite la procédure d'installation du projet courant comme le ferait un nouveau développeur :

- clone frais et isolé (nom de projet Docker Compose dédié, aucun conteneur existant touché) ;
- exécution littérale de la documentation, puis vérification que l'application tourne vraiment ;
- revue statique de portabilité macOS / Ubuntu ;
- nettoyage systématique, rapport avec bloquants et trous de documentation.

Sans argument, audite le commit courant. `/onboarding:check-install origin/main` audite ce qu'un nouveau clonerait.

Prérequis : Docker avec Compose v2, git. Testé sur : à compléter.

## Développement

```
claude plugin validate ./plugins/onboarding
claude --plugin-dir ./plugins/onboarding
```

Après une modification : `/reload-plugins`.
