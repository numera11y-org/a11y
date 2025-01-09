# Sections sémantiques

## Principes généraux

Les sections sémantiques telles que `<header>`, `<footer>`, `<article>`, et `<section>` permettent d'organiser le contenu de manière logique pour faciliter la navigation des utilisateurs et des technologies d'assistance.

## Exemple typique

```html
<article>
  <header>
    <h2>Titre de l'article</h2>
  </header>
  <p>Contenu principal de l'article.</p>
  <footer>
    Publié le 8 janvier 2025.
  </footer>
</article>
```

## Bonnes pratiques

- **Utilisation cohérente :**
  - Utilisez `<header>` et `<footer>` pour délimiter les sections ou en-têtes des articles.
  - Préférez `<section>` pour grouper des contenus similaires au sein d'une page.
- **Titres descriptifs :** Chaque section doit avoir un titre pertinent pour faciliter la compréhension.

## Accessibilité avancée

- **Navigation ARIA :** Ajoutez `role="region"` ou `aria-labelledby` pour permettre une navigation claire et rapide.

### Exemple

```html
<section aria-labelledby="services-title">
  <h2 id="services-title">Nos services</h2>
  <p>Nous proposons des solutions adaptées à vos besoins.</p>
</section>
```

- **Structure imbriquée :** Assurez une hiérarchie logique pour les utilisateurs de lecteurs d'écran.

### Exemple

```html
<section>
  <header>
    <h2>Section principale</h2>
  </header>
  <article>
    <h3>Sous-section</h3>
    <p>Contenu de la sous-section.</p>
  </article>
</section>
```

