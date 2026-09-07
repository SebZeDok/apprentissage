# apprentissage

Application web personnelle de suivi d'apprentissage (« Mon Apprentissage 📚 »).

## Nature du projet

- **Un seul fichier** : `index.html` (HTML + CSS + JS inline, ~2700 lignes). Pas de build, pas de framework, pas de gestionnaire de paquets.
- **Dépendance externe unique** : Chart.js chargé depuis cdnjs (`https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js`).
- **Pas de backend.** Toutes les données sont stockées dans le `localStorage` du navigateur de chaque utilisateur. Aucune synchro entre appareils. L'appli propose un export/import JSON qui sert de sauvegarde manuelle.

## Déploiement

- Hébergé sur **GitHub Pages** : https://sebzedok.github.io/apprentissage/
- Source : branche `main`, racine du dépôt. Le dépôt est **public** (obligatoire pour Pages sur le plan gratuit).
- HTTPS forcé.

### Mettre à jour le site

Éditer `index.html`, puis :

```bash
git add index.html && git commit -m "..." && git push
```

Pages se reconstruit automatiquement (~1 min).

## Faire évoluer l'appli

- Tout se passe dans `index.html`. Chercher la section concernée (le fichier est structuré : styles en `<style>`, écrans/markup, puis un gros bloc `<script>`).
- Garder le principe « un seul fichier autonome » sauf décision explicite du contraire.
- Le fichier d'origine livré par l'utilisateur était `learning-tracker-20.html` ; `index.html` en est la copie déployée.

## Évolution structurante à connaître

Si l'utilisateur veut des **comptes, une synchro multi-appareils ou des données partagées**, il faut introduire un backend (ex. Supabase). C'est un changement d'architecture, pas une simple retouche.
