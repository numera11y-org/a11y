# Élément `<article>` en HTML accessible

## Principes généraux

Pour rendre un élément `<article>` accessible, il faut respecter ces principes :

- Utiliser `<article>` pour du contenu autonome et indépendant
- Structurer le contenu avec des titres et paragraphes appropriés
- Fournir un titre principal pour chaque `<article>`
- S'assurer que le contenu a du sens hors de son contexte

## Exemple typique

```html
<article>
  <h2>Titre de l'article</h2>
  <p>Contenu de l'article...</p>
  <footer>
    <p>Publié le <time datetime="2025-01-10">10 janvier 2025</time> par Jean Dupont</p>
  </footer>
</article>
```

## Utilisation avancée

### Article imbriqué

```html
<article>
  <h2>Article principal</h2>
  <p>Contenu de l'article principal...</p>

  <article>
    <h3>Article secondaire</h3>
    <p>Contenu de l'article secondaire...</p>
  </article>
</article>
```

### Article avec sections

```html
<article>
  <h2>Guide de voyage : Guadeloupe</h2>

  <section>
    <h3>Monuments à visiter</h3>
    <p>Liste des principaux monuments...</p>
  </section>

  <section>
    <h3>Où manger</h3>
    <p>Recommandations de restaurants...</p>
  </section>
</article>
```

## Bonnes pratiques

- Utiliser une structure de titres logique à l'intérieur de `<article>`
- Inclure des métadonnées pertinentes (auteur, date de publication, etc.)
- S'assurer que le contenu est compréhensible indépendamment du reste de la page
- Éviter d'utiliser `<article>` pour des éléments non autonomes

## Accessibilité avancée

### Utilisation d'ARIA pour améliorer la sémantique

```html
<article aria-labelledby="article-title">
  <h2 id="article-title">Titre de l'article</h2>
  <p>Contenu de l'article...</p>
</article>
```

## Navigation au clavier

L'élément `<article>` n'a pas d'impact direct sur la navigation au clavier. Cependant, assurez-vous que les liens et les éléments interactifs à l'intérieur de l'article sont accessibles au clavier.

## Checklist pour l'audit d'accessibilité

1. Vérifier que `<article>` est utilisé pour du contenu autonome
2. S'assurer que chaque `<article>` a un titre principal
3. Contrôler la structure logique des titres à l'intérieur de `<article>`
4. Vérifier la présence de métadonnées pertinentes
5. Tester la compréhension du contenu hors contexte

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs à la structure de l'information
2. Respect des niveaux de conformité visés (A, AA, AAA)
3. Documentation des non-conformités éventuelles et des solutions proposées

### Outils et méthodes

1. Inspection visuelle du code HTML pour vérifier l'utilisation correcte de `<article>`
2. Utilisation d'outils de validation d'accessibilité automatisés
3. Test avec différents lecteurs d'écran pour vérifier la compréhension du contenu
4. Vérification de l'affichage et du comportement sur différents navigateurs et appareils

En suivant ces recommandations, vous vous assurez que vos éléments `<article>` sont accessibles et conformes aux normes WCAG et RGAA, offrant ainsi une expérience inclusive pour tous les utilisateurs.
