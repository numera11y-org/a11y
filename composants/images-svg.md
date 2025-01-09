## Images et SVG accessibles en HTML

### Principes généraux

Pour rendre une image ou un SVG accessible, il faut respecter ces principes :

- Fournir une alternative textuelle pertinente
- Distinguer les éléments décoratifs des éléments informatifs
- Utiliser les attributs appropriés selon le type d'image ou de SVG
- Assurer une description détaillée pour les images complexes

### Images bitmap (JPG, PNG, GIF, etc.)

#### Exemple typique

```html
<img src="chemin/vers/image.jpg" alt="Description de l'image">
```

- `src` : indique le chemin vers le fichier image
- `alt` : fournit une alternative textuelle

#### Images informatives simples

```html
<img src="logo-entreprise.png" alt="Logo de l'entreprise XYZ">
```

#### Images décoratives

```html
<img src="separateur.png" alt="">
```

#### Images complexes

```html
<img src="graphique-ventes.png" alt="Graphique des ventes 2023" aria-describedby="desc-graphique">
<p id="desc-graphique">Ce graphique montre l'évolution des ventes sur l'année 2023, avec un pic en juillet et une baisse en décembre.</p>
```

#### Images-liens

```html
<a href="accueil.html">
  <img src="logo-accueil.png" alt="Retour à l'accueil">
</a>
```

#### Utilisation de `figure` et `figcaption`

```html
<figure>
  <img src="photo-equipe.jpg" alt="L'équipe de développement au complet">
  <figcaption>Notre équipe lors de la conférence annuelle 2023</figcaption>
</figure>
```

#### Boutons images

```html
<input type="image" src="bouton-recherche.png" alt="Lancer la recherche">
```

## Images responsives et optimisées pour les écrans haute résolution

### Utilisation de l'attribut srcset

L'attribut `srcset` permet de spécifier plusieurs sources d'images pour différentes résolutions d'écran :

```html
<img src="image-small.jpg"
     srcset="image-small.jpg 300w,
             image-medium.jpg 600w,
             image-large.jpg 1200w"
     alt="Description de l'image">
```

### Utilisation de l'attribut sizes

L'attribut `sizes` complète `srcset` en indiquant la taille d'affichage de l'image selon la largeur du viewport :

```html
<img src="image-small.jpg"
     srcset="image-small.jpg 300w,
             image-medium.jpg 600w,
             image-large.jpg 1200w"
     sizes="(max-width: 320px) 280px,
            (max-width: 640px) 580px,
            1100px"
     alt="Description de l'image">
```

### Utilisation de l'élément picture pour l'art direction

L'élément `picture` permet de fournir différentes versions d'une image selon les caractéristiques de l'écran :

```html
<picture>
  <source media="(min-width: 800px)" srcset="image-large.jpg">
  <source media="(min-width: 500px)" srcset="image-medium.jpg">
  <img src="image-small.jpg" alt="Description de l'image">
</picture>
```

### Optimisation pour les écrans Retina

Pour les écrans haute résolution, on peut utiliser le descripteur de densité de pixels dans `srcset` :

```html
<img src="image.jpg"
     srcset="image.jpg 1x, image@2x.jpg 2x, image@3x.jpg 3x"
     alt="Description de l'image">
```

### Lazy loading natif

L'attribut `loading="lazy"` permet de différer le chargement des images hors écran :

```html
<img src="image.jpg" loading="lazy" alt="Description de l'image">
```

Ces techniques permettent d'optimiser le chargement des images en fonction des caractéristiques de l'appareil et de la connexion de l'utilisateur, améliorant ainsi les performances et l'expérience utilisateur. Il est important de les intégrer dans notre approche globale de l'accessibilité et de l'optimisation des images sur le web.

### Images vectorielles (SVG)

#### SVG informatif simple

```html
<svg role="img" aria-label="Logo de l'entreprise">
  <!-- contenu SVG -->
</svg>
```

#### SVG décoratif

```html
<svg aria-hidden="true" focusable="false">
  <!-- Contenu du SVG décoratif -->
</svg>
```

#### SVG avec titre accessible

```html
<svg role="img" aria-labelledby="svgTitle">
  <title id="svgTitle">Description concise de l'image SVG</title>
  <!-- Contenu du SVG -->
</svg>
```

#### SVG complexe avec description détaillée

```html
<svg role="img" aria-labelledby="svgTitle svgDesc">
  <title id="svgTitle">Titre court de l'image SVG</title>
  <desc id="svgDesc">Description détaillée du contenu et de la signification de l'image SVG.</desc>
  <!-- Contenu du SVG -->
</svg>
```

#### SVG en tant que lien ou bouton

```html
<a href="/">
  <svg role="img" aria-label="Accueil">
    <!-- Contenu du SVG -->
  </svg>
</a>
```

### Bonnes pratiques supplémentaires

- Utilisez des noms de fichiers descriptifs pour les images
- Assurez-vous que le texte dans les images a un contraste suffisant
- Évitez d'utiliser des images pour représenter du texte
- Testez vos pages avec des lecteurs d'écran pour vérifier l'accessibilité
- Pour les SVG complexes, envisagez de fournir une version alternative en texte ou en image bitmap avec une description détaillée

### Checklist pour l'audit d'accessibilité des images et SVG

Lors d'un audit d'accessibilité, vérifiez les points suivants pour chaque image et SVG :

#### Images bitmap

1. Présence de l'attribut `alt` pour toutes les images
2. Pertinence du contenu de l'attribut `alt` :
   - Description appropriée pour les images informatives
   - Attribut vide pour les images décoratives
3. Utilisation correcte de `aria-describedby` pour les images complexes
4. Contraste suffisant pour le texte dans les images
5. Cohérence entre le texte de l'attribut `alt` et la fonction de l'image pour les images-liens
6. Utilisation appropriée de `figure` et `figcaption` pour les images avec légende

#### SVG

1. Présence de `role="img"` pour les SVG informatifs
2. Utilisation correcte de `aria-label` ou `aria-labelledby` pour fournir une alternative textuelle
3. Présence de `aria-hidden="true"` pour les SVG décoratifs
4. Utilisation de `<title>` et `<desc>` pour les SVG complexes
5. Cohérence entre le texte alternatif et la fonction du SVG pour les SVG servant de liens ou boutons

#### Vérifications générales

1. Absence d'images de texte (sauf exceptions justifiées)
2. Qualité et lisibilité des images
3. Cohérence des alternatives textuelles avec le contenu visuel
4. Vérification de l'accessibilité des contrôles pour les contenus interactifs (zoom, carrousel, etc.)
5. Test avec différentes technologies d'assistance (lecteurs d'écran, etc.)
6. Vérification de l'accessibilité sur différents appareils (desktop, mobile, tablette)

#### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux images (thématique 1)
2. Respect des niveaux de conformité visés (A, AA, AAA)
3. Documentation des non-conformités éventuelles et des solutions proposées

#### Outils et méthodes

1. Utilisation d'outils automatisés d'audit d'accessibilité
2. Inspection manuelle du code source
3. Tests utilisateurs avec des personnes en situation de handicap
4. Vérification de la base de référence définie (combinaisons de technologies d'assistance, systèmes d'exploitation et navigateurs)

En suivant cette checklist lors de l'audit, vous vous assurez de couvrir les principaux aspects de l'accessibilité des images et SVG, conformément aux exigences du RGAA et des WCAG. N'oubliez pas que cette vérification s'inscrit dans le cadre plus large d'un audit complet d'accessibilité, qui doit couvrir tous les aspects du site web ou de l'application.
