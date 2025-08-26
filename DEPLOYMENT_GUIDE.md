# Guide de Déploiement GitHub Pages

Ce guide vous explique étape par étape comment déployer votre portfolio sur GitHub Pages.

## 📋 Prérequis

- Un compte GitHub
- Git installé sur votre ordinateur
- Les fichiers du portfolio téléchargés

## 🚀 Déploiement étape par étape

### Étape 1 : Créer un repository GitHub

1. **Connectez-vous à GitHub** et cliquez sur "New repository"
2. **Nommez votre repository** :
   - Pour un site personnel : `votre-username.github.io`
   - Pour un projet : `nom-de-votre-portfolio`
3. **Configurez le repository** :
   - ✅ Public (obligatoire pour GitHub Pages gratuit)
   - ✅ Add a README file
   - ❌ Ne pas ajouter .gitignore (nous en avons déjà un)
4. Cliquez sur **"Create repository"**

### Étape 2 : Cloner le repository

```bash
# Remplacez par votre URL de repository
git clone https://github.com/votre-username/votre-portfolio.git
cd votre-portfolio
```

### Étape 3 : Ajouter les fichiers du portfolio

1. **Copiez tous les fichiers** du portfolio dans le dossier cloné :
   - `index.html`
   - `styles.css`
   - `script.js`
   - `README.md`
   - `.gitignore`
   - Dossier `assets/` (si présent)

2. **Vérifiez la structure** :
   ```
   votre-portfolio/
   ├── index.html
   ├── styles.css
   ├── script.js
   ├── README.md
   ├── .gitignore
   └── assets/
   ```

### Étape 4 : Pousser vers GitHub

```bash
# Ajouter tous les fichiers
git add .

# Créer un commit
git commit -m "Add portfolio website"

# Pousser vers GitHub
git push origin main
```

### Étape 5 : Activer GitHub Pages

1. **Allez dans votre repository** sur GitHub
2. **Cliquez sur "Settings"** (onglet en haut)
3. **Scrollez jusqu'à "Pages"** dans le menu de gauche
4. **Configurez la source** :
   - Source : "Deploy from a branch"
   - Branch : "main"
   - Folder : "/ (root)"
5. **Cliquez sur "Save"**

### Étape 6 : Accéder à votre site

Après quelques minutes, votre site sera disponible à :
- Site personnel : `https://votre-username.github.io`
- Site de projet : `https://votre-username.github.io/nom-du-repository`

## 🌐 Configuration avec domaine personnalisé

### Acheter un domaine

Vous pouvez acheter un domaine chez :
- Namecheap
- GoDaddy
- OVH
- Gandi

### Configurer le domaine

1. **Dans GitHub** :
   - Settings > Pages > Custom domain
   - Entrez votre domaine : `www.votre-domaine.com`
   - Cochez "Enforce HTTPS"

2. **Créer un fichier CNAME** :
   ```bash
   echo "www.votre-domaine.com" > CNAME
   git add CNAME
   git commit -m "Add custom domain"
   git push origin main
   ```

3. **Chez votre registrar** :
   Ajoutez ces enregistrements DNS :
   ```
   Type: CNAME
   Name: www
   Value: votre-username.github.io
   
   Type: A
   Name: @
   Value: 185.199.108.153
   Value: 185.199.109.153
   Value: 185.199.110.153
   Value: 185.199.111.153
   ```

## 🔧 Dépannage

### Problème : Site non accessible

**Solutions** :
- Vérifiez que `index.html` est à la racine
- Attendez 10-15 minutes après activation
- Vérifiez dans Actions si le déploiement a réussi

### Problème : CSS/JS ne se charge pas

**Solutions** :
- Vérifiez les chemins dans `index.html`
- Utilisez des chemins relatifs : `./styles.css`
- Vérifiez la casse des noms de fichiers

### Problème : Domaine personnalisé ne fonctionne pas

**Solutions** :
- Vérifiez les enregistrements DNS (propagation : 24-48h)
- Assurez-vous que le fichier CNAME existe
- Vérifiez l'orthographe du domaine

## 📈 Optimisations post-déploiement

### SEO et Performance

1. **Ajouter Google Analytics** :
   ```html
   <!-- Dans <head> -->
   <script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
   <script>
     window.dataLayer = window.dataLayer || [];
     function gtag(){dataLayer.push(arguments);}
     gtag('js', new Date());
     gtag('config', 'GA_MEASUREMENT_ID');
   </script>
   ```

2. **Ajouter un sitemap.xml** :
   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
     <url>
       <loc>https://votre-domaine.com/</loc>
       <lastmod>2024-01-01</lastmod>
       <priority>1.0</priority>
     </url>
   </urlset>
   ```

3. **Optimiser les images** :
   - Utilisez WebP quand possible
   - Compressez avec TinyPNG
   - Ajoutez des attributs `loading="lazy"`

### Sécurité

1. **Activer HTTPS** (automatique avec GitHub Pages)
2. **Ajouter des headers de sécurité** avec un `_headers` file :
   ```
   /*
     X-Frame-Options: DENY
     X-Content-Type-Options: nosniff
     Referrer-Policy: strict-origin-when-cross-origin
   ```

## 🔄 Mise à jour du site

Pour mettre à jour votre portfolio :

```bash
# Modifier vos fichiers localement
# Puis :
git add .
git commit -m "Update portfolio content"
git push origin main
```

Le site sera automatiquement mis à jour en quelques minutes.

## 📞 Support

Si vous rencontrez des problèmes :
1. Consultez la [documentation GitHub Pages](https://docs.github.com/en/pages)
2. Vérifiez les [status GitHub](https://www.githubstatus.com/)
3. Créez une issue dans ce repository

---

**Bon déploiement ! 🚀**

