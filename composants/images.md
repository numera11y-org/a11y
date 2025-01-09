## Images et SVG accessibles

### Principes généraux

Pour rendre une image ou un SVG accessible, il faut respecter ces principes :

- Fournir une alternative textuelle pertinente (`alt`).
- Distinguer les éléments décoratifs des éléments informatifs.
- Utiliser les rôles ARIA pour des descriptions complexes.

### Exemple typique

#### Images informatives

```html
<img src="logo.png" alt="Logo de l'entreprise">
```

#### Images décoratives

```html
<img src="decor.png" alt="">
```

### Bonnes pratiques

- Fournir une description précise et concise dans l'attribut `alt`.
- Utiliser `aria-hidden="true"` pour les images purement décoratives.
- Tester l'accessibilité avec des lecteurs d'écran pour vérifier l'annonce correcte.

### Accessibilité avancée

- **Description détaillée pour les images complexes :** Ajoutez `aria-describedby` pour fournir une description détaillée associée à l'image.

#### Exemple

```html
<img src="graphique.png" alt="Graphique des ventes 2023" aria-describedby="graphique-desc">
<p id="graphique-desc">Ce graphique montre l'évolution des ventes en 2023 avec un pic en juillet.</p>
```

- **SVG interactif :** Fournissez un contexte clair avec des balises `<title>` et `<desc>`.

#### Exemple

```html
<svg role="img" aria-labelledby="svgTitle svgDesc">
  <title id="svgTitle">Graphique des ventes</title>
  <desc id="svgDesc">Détails des ventes trimestrielles.</desc>
</svg>
```

