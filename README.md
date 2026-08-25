# Déployer Tuner M3U gratuitement

Le dossier ne contient qu'un seul fichier : `index.html` (ton app complète,
autonome — aucune dépendance à installer).

---

## Option A — GitHub Pages (durable, versionné)

### 1. Crée un dépôt sur GitHub
Va sur https://github.com/new, donne-lui un nom (ex. `tuner-m3u`), laisse-le
public, ne coche aucune case d'initialisation (pas de README/licence).

### 2. Pousse le fichier depuis ton terminal
Dans ce dossier (`tuner-deploy/`) :

```bash
git init
git add index.html
git commit -m "Premier déploiement de Tuner M3U"
git branch -M main
git remote add origin https://github.com/TON-PSEUDO/tuner-m3u.git
git push -u origin main
```

Remplace `TON-PSEUDO` et `tuner-m3u` par ton nom d'utilisateur GitHub et le
nom réel du dépôt.

### 3. Active GitHub Pages
Dans le dépôt sur GitHub : **Settings → Pages** → sous "Build and
deployment", choisis la branche `main` et le dossier `/ (root)` → **Save**.

### 4. Ton app est en ligne
Après 1-2 minutes, elle est accessible à :
```
https://TON-PSEUDO.github.io/tuner-m3u/
```

### Mettre à jour plus tard
Remplace `index.html`, puis :
```bash
git add index.html
git commit -m "Mise à jour"
git push
```
Le site se met à jour automatiquement en quelques minutes.

---

## Option B — Netlify Drop (le plus rapide, sans Git)

1. Va sur https://app.netlify.com/drop
2. Glisse le fichier `index.html` de ce dossier directement dans la page
3. Netlify te donne immédiatement une URL du type
   `https://nom-aleatoire.netlify.app`
4. Pour la garder après fermeture du navigateur, crée un compte gratuit
   Netlify et "claim" le site (bouton proposé juste après le déploiement)

---

## À savoir une fois en ligne

- **CORS** : certaines playlists M3U distantes refusent les requêtes
  cross-origin quel que soit l'hébergeur — l'import de fichier local reste
  la solution de secours si le chargement par URL échoue.
- **HTTPS** : les deux options servent le site en HTTPS par défaut, ce qui
  est nécessaire pour que `fetch()` fonctionne correctement vers des flux
  eux-mêmes en HTTPS.
- **Domaine personnalisé** : possible gratuitement sur les deux (Settings →
  Custom domain) si tu as un nom de domaine à toi.
