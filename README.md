# NutriFusion — Bilan NPK & Optimisation P

Application web autonome (un seul fichier `index.html`, sans backend) : Culture & Géolocalisation, NutriOptima (Bilan NPK), Phosfusion (Optimisation P), FertiPlan (Plan de Fertilisation N·P·K·Ca·Mg) et Catalogue de produits.

## Hébergement sur GitHub Pages — étapes

### 1. Créer le dépôt
1. Sur [github.com](https://github.com), clique sur **New repository**.
2. Donne-lui un nom, par exemple `nutrifusion`.
3. Laisse-le **Public** (obligatoire pour GitHub Pages gratuit, sauf compte GitHub Pro/Team/Enterprise).
4. Ne coche pas "Add a README" (on a déjà le nôtre) — clique **Create repository**.

### 2. Ajouter les fichiers
**Option A — via l'interface web (le plus simple, sans rien installer)**
1. Sur la page du dépôt fraîchement créé, clique **uploading an existing file**.
2. Glisse-dépose `index.html` (et `README.md` si tu veux).
3. En bas, écris un message de commit (ex. "Ajout de l'application"), puis **Commit changes**.

**Option B — via Git en ligne de commande**
```bash
git clone https://github.com/<ton-utilisateur>/nutrifusion.git
cd nutrifusion
# copie index.html (et README.md) dans ce dossier
git add .
git commit -m "Ajout de l'application"
git push
```

### 3. Activer GitHub Pages
1. Dans le dépôt, va dans **Settings** (onglet en haut).
2. Dans le menu de gauche, clique **Pages**.
3. Sous **Build and deployment** → **Source**, choisis **Deploy from a branch**.
4. Sous **Branch**, choisis `main` (ou `master`) et le dossier `/ (root)`, puis **Save**.
5. Attends 1 à 2 minutes — GitHub affiche ensuite en haut de cette page l'URL publique, du type :
   `https://<ton-utilisateur>.github.io/nutrifusion/`

### 4. Mettre à jour l'application plus tard
- **Option A (web)** : ouvre `index.html` dans le dépôt → icône crayon (Edit) → colle le nouveau contenu → **Commit changes**. Ou supprime l'ancien fichier et re-upload le nouveau avec le même nom.
- **Option B (Git)** : remplace `index.html` en local, puis :
  ```bash
  git add .
  git commit -m "Mise à jour"
  git push
  ```
- Le site se met à jour automatiquement (1-2 minutes) après chaque `push` ou commit sur la branche configurée.

## Notes techniques
- Fichier unique, aucune installation ni build nécessaire — GitHub Pages sert `index.html` tel quel.
- L'application charge Leaflet et Plotly depuis des CDN publics (`unpkg.com`, `cdn.plot.ly`) et interroge l'API publique **SoilGrids** (ISRIC) pour la géolocalisation du sol — une connexion internet est nécessaire à l'usage, mais aucune clé API n'est requise.
- Toutes les données saisies (catalogue de produits, besoins, résultats) vivent uniquement dans le navigateur de la personne qui utilise le site (aucune base de données, aucun stockage serveur) — chaque visiteur repart d'un catalogue par défaut à chaque nouvelle session/onglet.
