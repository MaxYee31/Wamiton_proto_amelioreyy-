[README.md](https://github.com/user-attachments/files/28680108/README.md)
# Wamiton — Prototype PWA

Prototype interactif de Wamiton, billetterie d'événements culturels béninois. Mobile-first, **100 % statique, aucun build nécessaire**.

Deux parcours dans une seule app :
- **Participant** — splash → exploration → fiche événement → achat → billet à code dynamique → profil.
- **Organisateur** — onboarding → tableau de bord → création d'événement (wizard 5 étapes) → suivi des ventes → reversements.

L'écran d'accueil (« Tu viens pour quoi ? ») laisse choisir l'espace.

## Contenu

| Fichier | Rôle |
|---|---|
| `index.html` | L'application complète (HTML + CSS + JS en un seul fichier) |
| `image-slot.js` | Composant des zones photo (glisser-déposer) — dépendance de `index.html` |
| `vercel.json` | Config de déploiement Vercel |
| `package.json` | Métadonnées + script de prévisualisation locale |

> Les polices (Google Fonts) sont chargées via CDN — une connexion internet est requise au premier chargement.

## Pour tes collègues : que tester ?

L'app démarre sur le splash puis « Tu viens pour quoi ? ». Pour l'**espace organisateur**, choisir **« J'organise »**.

On peut aussi ouvrir un écran précis directement via le paramètre `?s=` dans l'URL (pratique pour pointer un collègue vers un écran) :

| Écran | URL |
|---|---|
| Tableau de bord orga | `…/?s=odash` |
| Détail d'un événement | `…/?s=oevent` |
| Création (wizard) | `…/?s=ocreate` |
| Suivi des ventes | `…/?s=osales` |
| Reversements | `…/?s=opayout` |
| Profil organisateur | `…/?s=oprofile` |

> ⚠️ `?s=` **fige** l'écran (mode capture, pour partager une vue). Pour cliquer librement dans le parcours, ouvre l'URL **sans** paramètre.

### Recueillir les avis
Le prototype n'embarque pas d'outil de commentaire. Options simples :
- Partager l'URL Vercel et collecter les retours dans un fil (Slack / WhatsApp / doc partagé).
- Demander des captures annotées sur les écrans `?s=…` ci-dessus.

## Prévisualiser en local

```bash
# avec npx (Node installé)
npx serve .

# ou avec Python
python3 -m http.server 8000
```

Puis ouvre `http://localhost:8000`.

> Ouvrir `index.html` par double-clic fonctionne aussi, mais un petit serveur local est plus fidèle au déploiement.

## Déployer

### Option A — Vercel (recommandé)
1. Pousse ce dossier sur un dépôt GitHub.
2. Sur [vercel.com](https://vercel.com) → **Add New Project** → importe le dépôt.
3. Framework Preset : **Other**. Laisse les champs Build vides (site statique).
4. **Deploy**. C'est en ligne — partage l'URL à tes collègues.

### Option B — Netlify (le plus rapide, sans Git)
Glisse-dépose ce dossier sur [app.netlify.com/drop](https://app.netlify.com/drop). URL publique immédiate.

### Option C — GitHub Pages
1. Pousse sur GitHub.
2. **Settings → Pages → Source : Deploy from a branch** → branche `main`, dossier `/root`.
3. L'URL `https://<utilisateur>.github.io/<repo>/` est générée en quelques minutes.

## Mettre sur GitHub (rappel des commandes)

```bash
git init
git add .
git commit -m "Wamiton — prototype participant + organisateur"
git branch -M main
git remote add origin https://github.com/<utilisateur>/wamiton.git
git push -u origin main
```
