# BubiMate sur GitHub - Guide Complet

## Vue d'ensemble

Tu vas mettre ton app BubiMate sur GitHub et l'héberger sur **GitHub Pages** pour pouvoir la tester directement depuis une URL publique.

**Résultat final:** `https://ton-username.github.io/bubimate/`

---

## ÉTAPE 1: Créer un compte GitHub (si tu n'en as pas)

1. Ouvre https://github.com
2. Clique "Sign up"
3. Entre ton email (peut être nasshan@bubimex.com)
4. Crée un mot de passe
5. Choose username (ex: "dominik-bubi" ou ton vrai prénom)
6. Valide ton email

**Note:** Retiens ton username, tu en auras besoin!

---

## ÉTAPE 2: Créer un repository sur GitHub

1. Connecte-toi à https://github.com
2. Clique le "+" en haut à droite → "New repository"
3. **Repository name:** `bubimate` (en minuscules)
4. **Description:** "Field companion app for commercial visits - offline PWA"
5. **Public** (coché) - Important pour GitHub Pages
6. **Ne coche PAS** "Initialize this repository with README"
7. Clique **"Create repository"**

**Tu vois maintenant des instructions.** Continue avec ÉTAPE 3.

---

## ÉTAPE 3: Pousser le code depuis ton ordinateur

Ouvre un terminal/PowerShell sur ton ordinateur et fais ceci:

```bash
# Va dans le dossier BubiMate
cd /path/to/BubiMate

# Configure git avec ton nom/email GitHub
git config user.email "ton-email@example.com"
git config user.name "Ton Nom"

# Renomme la branche en 'main'
git branch -M main

# Ajoute le remote GitHub (remplace USERNAME par ton username!)
git remote add origin https://github.com/USERNAME/bubimate.git

# Pousse le code
git push -u origin main
```

**Remplace `USERNAME` par ton username GitHub!**

Exemple:
```bash
git remote add origin https://github.com/dominik-bubi/bubimate.git
```

---

## ÉTAPE 4: Authentifier auprès de GitHub

Quand tu fais `git push`, GitHub demande ton authentification.

### Option A: Personal Access Token (plus simple)

1. Sur GitHub, clique sur ton avatar (haut-droit) → Settings
2. Scroll down → "Developer settings" (bas à gauche)
3. "Personal access tokens" → "Tokens (classic)"
4. **"Generate new token"**
5. Donne-lui un nom: "BubiMate Deploy"
6. **Coche:** `repo` (full control of private repositories)
7. Clique **"Generate token"**
8. **Copie le token** (tu ne pourras le revoir qu'une fois!)
9. Quand `git push` demande ton mot de passe, **colle le token**

### Option B: SSH (plus sécurisé, mais complexe)

Si tu veux SSH, regarde: https://docs.github.com/en/authentication/connecting-to-github-with-ssh

---

## ÉTAPE 5: Activer GitHub Pages

Une fois le code poussé:

1. Sur GitHub.com, va à ton repo: `https://github.com/USERNAME/bubimate`
2. Clique **"Settings"** (onglet haut-droit)
3. Scroll down → **"Pages"** (dans le menu de gauche)
4. Sous "Build and deployment":
   - **Source:** Select "Deploy from a branch"
   - **Branch:** `main` (et `/root` folder)
5. Clique **"Save"**

**Attends 1-2 minutes...**

Tu dois voir un message vert: "Your site is live at `https://USERNAME.github.io/bubimate/`"

---

## ÉTAPE 6: Tester l'app en ligne

1. Ouvre https://USERNAME.github.io/bubimate/
2. L'app devrait charger immédiatement
3. Tout fonctionne **offline** - aucune connexion requise après le chargement initial

**Teste:**
- Sélectionne un client
- Clique "Arriver"
- Crée une action
- Ferme la visite
- Feedback modal
- Regarde le recap

**L'app est live! 🎉**

---

## ÉTAPE 7: Accéder depuis ton téléphone

### iPhone:

1. Ouvre Safari
2. Va à: `https://USERNAME.github.io/bubimate/`
3. Tape l'adresse et attends que l'app charge
4. Clique le bouton de partage (carré avec flèche)
5. Scroll down → **"Add to Home Screen"**
6. Donne un nom (ex: "BubiMate")
7. Clique **"Add"**

L'app est maintenant sur ton écran d'accueil comme une vraie app!

### Android:

1. Ouvre Chrome
2. Va à: `https://USERNAME.github.io/bubimate/`
3. Menu (3 points) → **"Install app"** (ou "Add to Home screen")
4. Clique **"Install"**

---

## ÉTAPE 8: Mettre à jour l'app (après modifications)

Quand tu fais des changements localement:

```bash
# Fait tes changements dans index.html ou autre

# Commit
git add .
git commit -m "Fix: description de ton changement"

# Pousse vers GitHub
git push
```

GitHub Pages se **met à jour automatiquement** en 1-2 minutes.

Rafraîchis ton navigateur (ou force le rafraîchissement: Cmd+Shift+R sur Mac, Ctrl+Shift+R sur Windows).

---

## Structure des fichiers

Voici ce qui est dans ton repo GitHub:

```
bubimate/
├── index.html          (app complète - 91KB)
├── sw.js               (service worker - offline)
├── manifest.webmanifest (PWA config)
├── icon.png            (icône app)
├── README.md           (documentation)
├── CODE-REVIEW.md      (analyse technique)
├── IMPROVEMENTS-ANALYSIS.md (idées futures)
├── GITHUB-SETUP.md     (ancien guide - ignore)
├── GITHUB-GUIDE.md     (ce fichier)
└── .git/               (historique git)
```

**Tout ce qu'il faut pour que l'app fonctionne est là.**

---

## Dépannage

### L'app ne charge pas

1. Attends 2 minutes après `git push`
2. Vide le cache du navigateur (Cmd/Ctrl + Shift + Delete)
3. Vérifie que le repo est **public**
4. Vérifie que la branche est **main**
5. Regarde "Settings" → "Pages" → le message de déploiement

### Les changements ne s'affichent pas

1. Assure-toi d'avoir fait `git push`
2. Attends 1-2 minutes
3. Force le rafraîchissement du navigateur: **Cmd+Shift+R** (Mac) ou **Ctrl+Shift+R** (Windows)

### GitHub demand un token/mot de passe

C'est normal! Utilise l'option A (Personal Access Token) du guide.

---

## Partager l'app

Tu peux maintenant partager le lien:

**Pour tester:** `https://USERNAME.github.io/bubimate/`

**Pour voir le code:** `https://github.com/USERNAME/bubimate`

Envoie le lien à qui tu veux - l'app fonctionne offline après le chargement initial!

---

## Workflow futur

Désormais, tu peux:

1. **Modifier localement** - change index.html, test dans le navigateur
2. **Commit:** `git add . && git commit -m "..."`
3. **Push:** `git push`
4. **Live en 2 minutes** sur GitHub Pages

Plus besoin d'envoyer des fichiers - tout est versionné et accessible en ligne!

---

## Notes importantes

✅ **L'app est 100% offline** - Une fois chargée, elle marche sans Internet
✅ **Données persistées localement** - IndexedDB stocke tout sur ton téléphone
✅ **Service Worker** - Cache automatique pour chargement rapide
✅ **GitHub Pages est gratuit** - Hébergement illimité pour repos publics
✅ **Domaine personnalisé** - Tu peux ajouter un domaine custom si tu veux (avancé)

---

## Commandes Git utiles

```bash
# Voir l'historique
git log --oneline

# Voir les changements pas encore committed
git status

# Voir ce qu'on va committer
git diff

# Revenir à la version précédente (pour un fichier)
git checkout HEAD -- index.html

# Revenir à un commit spécifique
git revert [commit-hash]
```

---

## Questions?

**Si ça bloque:** Prends une capture d'écran du message d'erreur et partage-la.

**Support GitHub:** https://docs.github.com/en

---

**Bon courage! L'app est maintenant en ligne. 🚀**

À très vite,
Dominik
