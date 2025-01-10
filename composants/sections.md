# Sections sémantiques en HTML accessible

## Élément `<header>`

### Principes généraux

- Utiliser `<header>` pour définir un en-tête contenant des informations introductives ou de navigation pour une page ou une section.
- Inclure des titres descriptifs et des éléments de navigation structurés pour garantir l'accessibilité.
- Ne pas imbriquer un `<header>` dans un autre `<header>`.

### Exemple typique

```html
<header>
  <h1>Bienvenue sur notre site</h1>
  <nav>
    <ul>
      <li><a href="#section1">Section 1</a></li>
      <li><a href="#section2">Section 2</a></li>
    </ul>
  </nav>
</header>
```

### Bonnes pratiques

1. Utiliser un seul `<header>` principal pour chaque page.
2. Fournir des titres clairs pour structurer les informations.

---

## Élément `<footer>`

### Principes généraux

- Utiliser `<footer>` pour regrouper des informations complémentaires ou des liens comme les mentions légales, les coordonnées, ou des liens vers des politiques importantes.
- Peut être utilisé pour un pied de page global ou local (par exemple, pour une section ou un article).

### Exemple typique

```html
<footer>
  <p>&copy; 2025 MonSite. Tous droits réservés.</p>
  <nav>
    <ul>
      <li><a href="/privacy">Politique de confidentialité</a></li>
      <li><a href="/terms">Conditions d’utilisation</a></li>
    </ul>
  </nav>
</footer>
```

### Bonnes pratiques

1. Inclure des liens vers des informations essentielles.
2. Éviter de dupliquer inutilement des contenus dans plusieurs pieds de page.

---

## Élément `<main>`

### Principes généraux

- Utiliser `<main>` pour regrouper le contenu principal de la page, excluant les éléments répétitifs comme les en-têtes, les pieds de page, ou les barres latérales.
- Chaque page doit avoir un seul élément `<main>` pour indiquer clairement son contenu principal.
- Faciliter la navigation directe vers `<main>` via des liens d’évitement, par exemple : "Aller au contenu principal".

### Exemple typique

```html
<a href="#main-content" class="skip-link">Aller au contenu principal</a>
<header>
  <h1>Bienvenue sur MonSite</h1>
</header>
<main id="main-content">
  <h2>Présentation</h2>
  <p>Notre site offre des solutions adaptées pour tous vos besoins.</p>
</main>
<footer>
  <p>&copy; 2025 MonSite. Tous droits réservés.</p>
</footer>
```

### Bonnes pratiques

1. Un seul `<main>` par page pour le contenu principal.
2. Inclure un lien d’évitement pour accéder rapidement au contenu principal.
3. Ne pas inclure `<main>` dans un `<section>` ou un autre conteneur.

---

## Élément `<article>`

### Principes généraux

- Utiliser `<article>` pour des contenus autonomes ou réutilisables, tels que des articles de blog, des commentaires, ou des fiches produit.
- Chaque `<article>` doit avoir un titre descriptif et être compréhensible indépendamment du reste de la page.

### Exemple typique

```html
<article>
  <header>
    <h2>Les meilleures pratiques d’accessibilité</h2>
    <p>Publié le 10 janvier 2025</p>
  </header>
  <p>L'accessibilité est un aspect clé de la conception web...</p>
  <footer>
    <p>Auteur : Jean Dupont</p>
  </footer>
</article>
```

### Bonnes pratiques

1. Inclure des informations pertinentes comme l’auteur, la date, et le contexte.
2. Fournir un titre explicite pour chaque article.

---

## Élément `<section>`

### Principes généraux

- Utiliser `<section>` pour diviser une page en groupes logiques de contenu ayant un thème commun.
- Chaque `<section>` doit être identifiable par un titre approprié (`<h2>`, `<h3>`, etc.).

### Exemple typique

```html
<section>
  <h2>À propos de nous</h2>
  <p>Notre mission est de rendre le web accessible à tous...</p>
</section>
```

### Bonnes pratiques

1. Fournir un titre clair pour chaque `<section>`.
2. Éviter d’utiliser `<section>` uniquement pour la mise en page visuelle.

---

## Accessibilité avancée

### Structuration des titres

- Assurer une hiérarchie logique des titres à travers les éléments `<header>`, `<section>`, `<article>`, et `<main>`.
- Un seul `<h1>` par page pour définir le titre principal.

### Navigation au clavier

- Inclure des liens d’évitement pour accéder rapidement au contenu principal (`<main>`).
- Les lecteurs d’écran doivent annoncer correctement les rôles des landmarks (`<header>`, `<footer>`, `<main>`, etc.).

### Ajout de landmarks avec ARIA

```html
<header role="banner">
  <h1>Page d'accueil</h1>
</header>
<main role="main">
  <section role="region" aria-labelledby="about-us">
    <h2 id="about-us">À propos de nous</h2>
    <p>Notre mission est de rendre le web accessible à tous...</p>
  </section>
</main>
<footer role="contentinfo">
  <p>&copy; 2025 MonSite. Tous droits réservés.</p>
</footer>
```

---

## Checklist pour l'audit d'accessibilité

1. Chaque `<header>`, `<footer>`, `<main>`, `<article>`, et `<section>` est utilisé de manière sémantique et logique.
2. Les titres sont présents et correctement structurés dans chaque élément.
3. L’élément `<main>` est unique et clairement défini comme contenu principal.
4. Les liens d’évitement permettent un accès rapide au contenu principal.
5. Les landmarks ARIA sont utilisés lorsque nécessaire pour renforcer l’accessibilité.
6. Les lecteurs d’écran annoncent correctement les rôles et contenus des landmarks.

---

### Conformité RGAA

1. Vérification de la conformité avec les critères RGAA relatifs à la structuration sémantique.
2. Respect des niveaux de conformité visés (A, AA, AAA).
3. Documentation des non-conformités éventuelles et des solutions proposées.

---

### Outils et méthodes

1. Utiliser des outils comme Axe ou Wave pour vérifier la structure des landmarks.
2. Tester la navigation au clavier pour chaque landmark.
3. Vérifier avec des lecteurs d’écran (NVDA, JAWS, VoiceOver) pour s'assurer que les sections sont bien annoncées.

En suivant ces recommandations, vos éléments `<header>`, `<footer>`, `<main>`, `<article>`, et `<section>` seront accessibles et conformes aux normes WCAG et RGAA, garantissant une expérience utilisateur inclusive et efficace.
