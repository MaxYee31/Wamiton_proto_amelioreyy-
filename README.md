# Wamiton — Prototype PWA

Prototype interactif du parcours Wamiton (participant) : du splash au billet, en passant par l'exploration, l'achat et le profil. 100 % statique, **aucun build nécessaire**.

## Contenu

| Fichier | Rôle |
|---|---|
| `index.html` | L'application complète (HTML + CSS + JS en un seul fichier) |
| `image-slot.js` | Composant des zones photo (glisser-déposer) utilisé par les écrans événement |
| `vercel.json` | Config de déploiement Vercel |
| `package.json` | Métadonnées + script de prévisualisation locale |

> Les polices (Google Fonts) sont chargées via CDN — une connexion internet est requise au premier chargement.

## Prévisualiser en local

Au choix :

```bash
# avec npx (Node installé)
npx serve .

# ou avec Python
python3 -m http.server 8000
```

Puis ouvre `http://localhost:8000` (ou l'URL affichée).

> Ouvrir `index.html` directement par double-clic fonctionne aussi, mais passer par un petit serveur local est plus fidèle au déploiement.

## Déployer

### Option A — Vercel (recommandé)
1. Pousse ce dossier sur un dépôt GitHub.
2. Sur [vercel.com](https://vercel.com) → **Add New Project** → importe le dépôt.
3. Framework Preset : **Other**. Laisse les champs Build vides (site statique).
4. **Deploy**. C'est en ligne.

### Option B — GitHub Pages
1. Pousse sur GitHub.
2. **Settings → Pages → Source : Deploy from a branch** → branche `main`, dossier `/root`.
3. L'URL `https://<utilisateur>.github.io/<repo>/` est générée en quelques minutes.

### Option C — Netlify
Glisse-dépose ce dossier sur [app.netlify.com/drop](https://app.netlify.com/drop).

## Mettre sur GitHub (rappel des commandes)

```bash
git init
git add .
git commit -m "Wamiton prototype"
git branch -M main
git remote add origin https://github.com/<utilisateur>/wamiton.git
git push -u origin main
```
