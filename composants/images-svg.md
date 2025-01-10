# Élément `<img>` en HTML accessible

## Principes généraux

Pour rendre un élément `<img>` accessible :

- Fournir un texte alternatif via l’attribut `alt` décrivant brièvement l'image pour les utilisateurs de technologies d’assistance.
- Si l’image est purement décorative, utiliser `alt=""` pour l’ignorer par les lecteurs d’écran.
- Utiliser `aria-hidden="true"` pour cacher les images décoratives ou redondantes des technologies d’assistance.
- Fournir des légendes via `<figcaption>` lorsqu'une explication ou un contexte supplémentaire est nécessaire.

## Exemple typique

```html
<img src="photo-profil.jpg" alt="Photo de profil de Marie Dupont" />
```

## Utilisation avancée

### Images décoratives

```html
<img src="background.jpg" alt="" aria-hidden="true" />
```

### Images avec légende

```html
<figure>
  <img src="chart.png" alt="Graphique montrant l'évolution des ventes trimestrielles." />
  <figcaption>Graphique : Évolution des ventes (2023).</figcaption>
</figure>
```

### Fallback pour les images manquantes

```html
<img src="logo.png" alt="Logo de l'entreprise" onerror="this.src='logo-placeholder.png'" />
```

## Bonnes pratiques

- Décrire la fonction ou le contenu essentiel de l'image, pas uniquement son apparence.
- Limiter l’usage de texte dans les images ; privilégier du texte HTML accessible.
- Tester les descriptions alternatives avec des lecteurs d’écran.

---

# Élément `<svg>` en HTML accessible

## Principes généraux

Pour rendre un élément `<svg>` accessible :

- Fournir un titre descriptif avec `<title>` et, si nécessaire, des descriptions supplémentaires avec `<desc>`.
- Utiliser l’attribut `role="img"` pour indiquer que l'élément SVG est une image.
- S’assurer que les SVG décoratifs sont masqués des technologies d’assistance via `aria-hidden="true"`.
- Éviter d'intégrer des éléments de texte essentiels directement dans le SVG ; utiliser des descriptions accessibles dans le DOM.

## Exemple typique

### SVG avec description

```html
<svg role="img" xmlns="http://www.w3.org/2000/svg" width="100" height="100">
  <title>Icône d'une étoile</title>
  <desc>Une étoile à cinq branches utilisée pour indiquer une note.</desc>
  <polygon points="50,15 61,35 85,35 66,50 72,75 50,60 28,75 34,50 15,35 39,35" fill="gold" />
</svg>
```

### SVG décoratif

```html
<svg aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="50" height="50">
  <circle cx="25" cy="25" r="20" fill="blue" />
</svg>
```

### SVG inclus dans un bouton

```html
<button aria-label="Télécharger">
  <svg role="img" xmlns="http://www.w3.org/2000/svg" width="16" height="16">
    <title>Icône de téléchargement</title>
    <path d="M8 0l4 4H9v7H7V4H4l4-4z" fill="currentColor" />
  </svg>
</button>
```

## Bonnes pratiques

- Toujours inclure une description dans `<title>` et `<desc>` pour les SVG significatifs.
- Masquer les SVG décoratifs avec `aria-hidden="true"`.
- S’assurer que les couleurs et contrastes utilisés dans les SVG respectent les critères d’accessibilité.

---

## Navigation au clavier

Les images et SVG ne sont généralement pas interactifs, sauf s’ils sont intégrés dans un composant interactif comme un bouton ou un lien. Pour garantir leur accessibilité :

- Les éléments interactifs doivent être navigables avec **Tab**.
- Ajouter un texte alternatif (`alt` ou ARIA) pour les éléments intégrés dans des composants.

## Checklist pour l'audit d'accessibilité

### Images `<img>`

1. Tous les éléments `<img>` ont un attribut `alt` pertinent.
2. Les images décoratives utilisent `alt=""` ou `aria-hidden="true"`.
3. Les images avec une fonction ou un contenu essentiel sont correctement décrites.
4. Les légendes associées sont utilisées avec `<figcaption>` lorsque nécessaire.

### SVG

1. Les SVG significatifs incluent un `<title>` et, si nécessaire, un `<desc>`.
2. Les SVG décoratifs sont masqués des technologies d’assistance avec `aria-hidden="true"`.
3. Les SVG interactifs sont intégrés dans des composants accessibles (ex. boutons).
4. Les contrastes de couleurs des SVG respectent les normes WCAG (minimum 4,5:1).

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux images et contenus non textuels.
2. Respect des niveaux de conformité visés (A, AA, AAA).
3. Documentation des non-conformités éventuelles et des solutions proposées.

### Outils et méthodes

1. Utiliser des extensions comme Axe ou Wave pour tester les descriptions des images et SVG.
2. Vérifier les contrastes avec des outils comme Colour Contrast Analyser.
3. Tester avec des lecteurs d’écran (NVDA, JAWS, VoiceOver) pour s'assurer que les descriptions sont annoncées correctement.

En suivant ces recommandations, vos images et SVG seront accessibles, garantissant une expérience utilisateur inclusive et conforme aux normes WCAG et RGAA.
