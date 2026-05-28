# Coffre n°1 — Bannière volée

Page statique pour le Rallye des Familles 2026. Style journal *L'Équipe* cohérent avec le livret.

## Contenu
- `index.html` — page complète, auto-contenue (HTML/CSS/JS inline, fonts Google)
- `assets/banniere-fragment.png` — premier fragment de la bannière

## Scénario
- **Page initiale** : morceau de bannière caché dans le coffre, indice = compo Spurs vs Celtics.
- **Après ouverture** (bonne combinaison) : révèle le **numéro mystère** `+1 (470) 441-7635` (lien `sms:`) + mission (envoyer le nom du sport par SMS → coordonnées GPS).

## À personnaliser avant publication
1. Optionnel : changer `FRAGMENT 1 / 6` (CSS `.fragment::after content`).
2. Le numéro `+1 (470) 441-7635` est déjà câblé (lien `sms:+14704417635`).

## Déploiement GitHub Pages (recommandé — gratuit, 2 min)
```bash
cd coffre-banniere
git init
git add .
git commit -m "Coffre n°1 — bannière volée"
gh repo create rallye-2026-coffre-01 --public --source=. --push
gh api -X POST /repos/:owner/rallye-2026-coffre-01/pages -f source[branch]=main -f source[path]=/
```
URL finale : `https://<user>.github.io/rallye-2026-coffre-01/`

## Déploiement Railway (alternative)
Railway accepte un site statique via un `Dockerfile` ou template `static`. Pour une page unique, GitHub Pages est plus simple.

## Test local
```bash
cd coffre-banniere
python3 -m http.server 8000
# puis ouvrir http://localhost:8000
```
