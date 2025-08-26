# Portfolio Professionnel

Un site web portfolio moderne et responsive, conçu pour présenter vos projets et compétences de manière élégante et professionnelle.

## 🌟 Caractéristiques

- **Design moderne et minimaliste** - Interface épurée avec animations fluides
- **Entièrement responsive** - Optimisé pour tous les appareils (desktop, tablette, mobile)
- **Animations interactives** - Effets de scroll, transitions et micro-interactions
- **Filtrage de projets** - Système de filtres pour organiser vos réalisations
- **Formulaire de contact** - Interface de contact avec validation
- **Optimisé pour GitHub Pages** - Déploiement simple et gratuit

## 🚀 Déploiement sur GitHub Pages

### Méthode 1 : Déploiement direct

1. **Créer un nouveau repository sur GitHub**
   ```bash
   # Cloner ou créer votre repository
   git clone https://github.com/votre-username/votre-portfolio.git
   cd votre-portfolio
   ```

2. **Copier les fichiers du portfolio**
   - Copiez tous les fichiers de ce projet dans votre repository
   - Assurez-vous que `index.html` est à la racine

3. **Pousser vers GitHub**
   ```bash
   git add .
   git commit -m "Initial portfolio commit"
   git push origin main
   ```

4. **Activer GitHub Pages**
   - Allez dans Settings > Pages de votre repository
   - Sélectionnez "Deploy from a branch"
   - Choisissez "main" branch et "/ (root)"
   - Cliquez sur "Save"

### Méthode 2 : Avec domaine personnalisé

1. Suivez les étapes de la Méthode 1
2. Dans Settings > Pages, ajoutez votre domaine personnalisé
3. Créez un fichier `CNAME` à la racine avec votre domaine :
   ```
   votre-domaine.com
   ```

## 🛠️ Personnalisation

### Informations personnelles

Modifiez les sections suivantes dans `index.html` :

- **Titre et nom** : Ligne 51-54
- **Description** : Ligne 55-58
- **À propos** : Ligne 78-88
- **Statistiques** : Ligne 90-102
- **Projets** : Ligne 130-220
- **Compétences** : Ligne 260-340
- **Contact** : Ligne 380-420

### Couleurs et style

Dans `styles.css`, modifiez les variables CSS :

```css
:root {
  --primary-color: #2563eb;    /* Couleur principale */
  --secondary-color: #1e293b;  /* Couleur secondaire */
  --accent-color: #f59e0b;     /* Couleur d'accent */
  --text-color: #0f172a;       /* Couleur du texte */
  --bg-color: #ffffff;         /* Couleur de fond */
}
```

### Ajout de projets

Pour ajouter un nouveau projet, copiez cette structure dans la section projets :

```html
<div class="project-card" data-category="web">
    <div class="project-image">
        <div class="project-overlay">
            <div class="project-links">
                <a href="lien-demo" class="project-link" aria-label="Voir le projet">
                    <!-- Icône externe -->
                </a>
                <a href="lien-github" class="project-link" aria-label="Code source">
                    <!-- Icône GitHub -->
                </a>
            </div>
        </div>
    </div>
    <div class="project-content">
        <h3 class="project-title">Nom du Projet</h3>
        <p class="project-description">Description du projet...</p>
        <div class="project-tech">
            <span class="tech-tag">React</span>
            <span class="tech-tag">Node.js</span>
        </div>
    </div>
</div>
```

## 📁 Structure des fichiers

```
portfolio_project/
├── index.html          # Page principale
├── styles.css          # Styles CSS
├── script.js           # JavaScript
├── README.md           # Documentation
├── assets/             # Ressources
│   ├── images/         # Images du site
│   └── icons/          # Icônes
└── screenshots/        # Captures d'écran (optionnel)
```

## 🎨 Fonctionnalités techniques

- **HTML5 sémantique** - Structure accessible et SEO-friendly
- **CSS3 moderne** - Flexbox, Grid, animations CSS
- **JavaScript vanilla** - Pas de dépendances externes
- **Responsive design** - Mobile-first approach
- **Performance optimisée** - Images optimisées, CSS/JS minifiés
- **Accessibilité** - Navigation au clavier, contrastes appropriés

## 🔧 Optimisations possibles

### Performance
- Compresser les images avec des outils comme TinyPNG
- Minifier CSS et JavaScript pour la production
- Utiliser un CDN pour les fonts Google

### SEO
- Ajouter des meta tags Open Graph
- Optimiser les balises title et description
- Ajouter un sitemap.xml

### Fonctionnalités avancées
- Ajouter un mode sombre
- Intégrer Google Analytics
- Ajouter un blog avec Jekyll
- Implémenter un système de commentaires

## 🌐 Compatibilité

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ✅ Mobile (iOS Safari, Chrome Mobile)

## 📝 Licence

Ce projet est sous licence MIT. Vous êtes libre de l'utiliser, le modifier et le distribuer.

## 🤝 Contribution

Les contributions sont les bienvenues ! N'hésitez pas à :
- Signaler des bugs
- Proposer des améliorations
- Soumettre des pull requests

## 📞 Support

Si vous avez des questions ou besoin d'aide :
- Créez une issue sur GitHub
- Consultez la documentation
- Contactez-moi via le formulaire du portfolio

---

**Fait avec ❤️ pour la communauté des développeurs**

