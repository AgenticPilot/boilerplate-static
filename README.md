# boilerplate-static

Boilerplate pour monorepos statiques **multi-applications** déployés sur GitHub Pages (HTML, CSS et JavaScript natifs, sans framework ni bundler). Il fournit une base commune (outillage, serveur de dev, conventions, tests) pour des projets composés d'une page d'accueil et d'applications dans `apps/`, avec des composants partagés dans `packages/`.

## Principes

- **Statique** : les fichiers servis sont ceux du dépôt (landing `index.html`, `apps/<slug>/`, `packages/`, assets).
- **Composants UI** : utiliser la bibliothèque [`@kewinmarchand/boilerplates-ui`](https://github.com/kewinMarchand/boilerplates-ui) (tokens, CSS, comportements vanilla) pour les composants génériques. N'ajouter des composants spécifiques au projet que lorsqu'ils sont vraiment propres au domaine (ex. cadre de jeu/app).
- **GitHub Pages** : structure compatible avec un déploiement Pages (racine du dépôt ou dossier configuré).

## Structure

- `index.html` / `landing.css` : page d'accueil (portail).
- `apps/<slug>/` : applications/pages indépendantes.
- `packages/` : code partagé du projet (thème, UI spécifique, utilitaires).
- `scripts/` : serveur de développement et helpers.
- `tests/` : tests unitaires, e2e et accessibilité (smoke) adaptés au monorepo.

## Démarrage

```bash
yarn install
yarn dev
```

Le serveur de développement sert la racine du dépôt sur `http://localhost:4098`.

## Qualité

```bash
yarn lint        # HTML, CSS, JS
yarn format:check
yarn test:unit
yarn test:e2e    # nécessite Playwright
yarn test:a11y
```

## Utilisation comme base

1. Copier/adopter la structure et les scripts dans le monorepo cible.
2. Déclarer la dépendance `@kewinmarchand/boilerplates-ui` et importer ses tokens/CSS/comportements vanilla pour les composants génériques.
3. Conserver en `packages/` uniquement les composants/thèmes réellement spécifiques au projet.
4. Adapter `site.config.json` et les tests à la liste réelle des apps/pages.
