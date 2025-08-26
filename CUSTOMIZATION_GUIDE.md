# Guide de Personnalisation

Ce guide vous aide à personnaliser votre portfolio selon vos besoins et votre identité visuelle.

## 🎨 Personnalisation du design

### Couleurs

Modifiez les couleurs principales dans `styles.css` :

```css
/* Recherchez ces variables dans le fichier CSS et modifiez-les */

/* Couleur principale (boutons, liens) */
background: linear-gradient(135deg, #2563eb, #3b82f6);
/* Remplacez par vos couleurs : */
background: linear-gradient(135deg, #your-color-1, #your-color-2);

/* Couleur du texte principal */
color: #0f172a;

/* Couleur du texte secondaire */
color: #64748b;

/* Couleur d'accent (formes géométriques) */
background: linear-gradient(135deg, #f59e0b, #f97316);
```

### Typographie

Pour changer la police, modifiez dans `index.html` :

```html
<!-- Remplacez la ligne Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">

<!-- Par votre police préférée, par exemple : -->
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

Puis dans `styles.css` :
```css
body {
    font-family: 'Poppins', sans-serif; /* Remplacez 'Inter' */
}
```

## 📝 Personnalisation du contenu

### Section Hero

Dans `index.html`, lignes 51-65 :

```html
<h1 class="hero-title">
    Bonjour, je suis
    <span class="hero-name">Votre Nom</span> <!-- Changez ici -->
</h1>
<p class="hero-description">
    Votre description personnelle... <!-- Changez ici -->
</p>
```

### Section À propos

Lignes 78-88, modifiez :
- Votre présentation personnelle
- Vos années d'expérience
- Vos statistiques

```html
<p>
    Votre présentation personnelle...
</p>

<div class="stat">
    <span class="stat-number">XX+</span> <!-- Vos chiffres -->
    <span class="stat-label">Vos réalisations</span>
</div>
```

### Projets

Pour chaque projet (lignes 130-220), modifiez :

```html
<div class="project-card" data-category="web"> <!-- Catégorie : web, mobile, design -->
    <div class="project-content">
        <h3 class="project-title">Nom de votre projet</h3>
        <p class="project-description">
            Description de votre projet...
        </p>
        <div class="project-tech">
            <span class="tech-tag">Technologie 1</span>
            <span class="tech-tag">Technologie 2</span>
        </div>
    </div>
</div>
```

**Liens des projets** :
```html
<a href="https://votre-demo.com" class="project-link" aria-label="Voir le projet">
<a href="https://github.com/votre-username/projet" class="project-link" aria-label="Code source">
```

### Compétences

Lignes 260-340, ajustez les pourcentages :

```html
<div class="skill-progress" data-width="95%"></div> <!-- Changez le pourcentage -->
```

Ajoutez de nouvelles compétences :
```html
<div class="skill-item">
    <span class="skill-name">Nouvelle Technologie</span>
    <div class="skill-bar">
        <div class="skill-progress" data-width="80%"></div>
    </div>
</div>
```

### Contact

Lignes 380-420, modifiez vos informations :

```html
<p>votre-email@exemple.com</p>
<p>+33 X XX XX XX XX</p>
<p>Votre Ville, Pays</p>
```

**Liens sociaux** :
```html
<a href="https://github.com/votre-username" class="social-link" aria-label="GitHub">
<a href="https://linkedin.com/in/votre-profil" class="social-link" aria-label="LinkedIn">
<a href="https://twitter.com/votre-handle" class="social-link" aria-label="Twitter">
```

## 🖼️ Ajout d'images

### Images de projets

1. **Créez un dossier** `assets/images/` dans votre projet
2. **Ajoutez vos captures d'écran** de projets
3. **Modifiez le CSS** pour afficher les images :

```css
.project-image {
    background-image: url('./assets/images/votre-projet.jpg');
    background-size: cover;
    background-position: center;
}
```

### Photo de profil

Pour ajouter votre photo dans la section hero :

```html
<!-- Remplacez la div hero-shape par : -->
<div class="hero-image">
    <img src="./assets/images/votre-photo.jpg" alt="Votre nom" class="profile-image">
</div>
```

Ajoutez ce CSS :
```css
.profile-image {
    width: 300px;
    height: 300px;
    border-radius: 50%;
    object-fit: cover;
    border: 5px solid #2563eb;
}
```

## 🎯 Fonctionnalités avancées

### Mode sombre

Ajoutez un bouton de basculement :

```html
<button id="theme-toggle" class="theme-toggle">🌙</button>
```

JavaScript pour le mode sombre :
```javascript
const themeToggle = document.getElementById('theme-toggle');
const body = document.body;

themeToggle.addEventListener('click', () => {
    body.classList.toggle('dark-theme');
    localStorage.setItem('theme', body.classList.contains('dark-theme') ? 'dark' : 'light');
});

// Charger le thème sauvegardé
if (localStorage.getItem('theme') === 'dark') {
    body.classList.add('dark-theme');
}
```

### Animations personnalisées

Modifiez les animations dans `styles.css` :

```css
/* Animation de la forme géométrique */
@keyframes float {
    0%, 100% { transform: translateY(0px) rotate(0deg); }
    50% { transform: translateY(-20px) rotate(5deg); }
}

/* Créez vos propres animations */
@keyframes votre-animation {
    /* Vos keyframes */
}
```

### Formulaire de contact fonctionnel

Pour un formulaire qui envoie vraiment des emails, utilisez un service comme :

1. **Formspree** :
```html
<form action="https://formspree.io/f/votre-id" method="POST">
```

2. **Netlify Forms** (si hébergé sur Netlify) :
```html
<form name="contact" method="POST" data-netlify="true">
```

## 📱 Personnalisation mobile

### Ajuster les tailles pour mobile

Dans `styles.css`, section `@media (max-width: 768px)` :

```css
@media (max-width: 768px) {
    .hero-title {
        font-size: 2rem; /* Ajustez selon vos besoins */
    }
    
    .section-title {
        font-size: 1.5rem;
    }
}
```

### Menu mobile personnalisé

Modifiez l'apparence du menu hamburger :

```css
.bar {
    background: #votre-couleur; /* Changez la couleur */
    height: 4px; /* Changez l'épaisseur */
}
```

## 🔧 Optimisations

### Performance

1. **Compresser les images** avec TinyPNG
2. **Minifier CSS/JS** pour la production :
   ```bash
   # Utilisez des outils comme :
   npm install -g clean-css-cli uglify-js
   cleancss -o styles.min.css styles.css
   uglifyjs script.js -o script.min.js
   ```

### SEO

Ajoutez dans `<head>` :
```html
<!-- Meta tags personnalisés -->
<meta name="description" content="Votre description SEO">
<meta name="keywords" content="vos, mots, clés">
<meta name="author" content="Votre Nom">

<!-- Open Graph -->
<meta property="og:title" content="Votre Nom - Portfolio">
<meta property="og:description" content="Votre description">
<meta property="og:image" content="./assets/images/og-image.jpg">
<meta property="og:url" content="https://votre-domaine.com">
```

## 🎨 Inspirations de couleurs

### Palettes modernes

1. **Bleu professionnel** (actuel)
   - Primaire : #2563eb
   - Secondaire : #1e293b
   - Accent : #f59e0b

2. **Vert nature**
   - Primaire : #059669
   - Secondaire : #064e3b
   - Accent : #f97316

3. **Violet créatif**
   - Primaire : #7c3aed
   - Secondaire : #1e1b4b
   - Accent : #f59e0b

4. **Rouge dynamique**
   - Primaire : #dc2626
   - Secondaire : #7f1d1d
   - Accent : #f59e0b

## 📋 Checklist de personnalisation

- [ ] Changer le nom et la description
- [ ] Modifier les couleurs du thème
- [ ] Ajouter vos projets réels
- [ ] Mettre à jour les compétences
- [ ] Ajouter vos informations de contact
- [ ] Configurer les liens sociaux
- [ ] Ajouter vos images/photos
- [ ] Tester sur mobile
- [ ] Optimiser pour le SEO
- [ ] Vérifier tous les liens

---

**Votre portfolio personnalisé est prêt ! 🎉**

