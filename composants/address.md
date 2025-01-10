# Élément `<address>` en HTML accessible

## Principes généraux

Pour rendre un élément `<address>` accessible, il faut respecter ces principes :

- Utiliser la balise pour indiquer les informations de contact de l'auteur ou du propriétaire du document/article
- S'assurer que le contenu est pertinent et se limite aux coordonnées
- Placer l'élément de manière appropriée dans la structure du document

## Exemple typique

```html
<address>
  Contact : <a href="mailto:contact@example.com">contact@example.com</a><br>
  Téléphone : +33 1 23 45 67 89<br>
  123 rue de l'Exemple, 75001 Paris
</address>
```

## Utilisation avancée

### Dans un article

```html
<article>
  <h1>Titre de l'article</h1>
  <p>Contenu de l'article...</p>
  <address>
    Par Jean Dupont<br>
    <a href="https://twitter.com/jeandupont">@jeandupont</a>
  </address>
</article>
```

### Dans le pied de page

```html
<footer>
  <address>
    Société Example<br>
    123 rue du Commerce<br>
    75001 Paris, France
  </address>
</footer>
```

## Bonnes pratiques

- Limiter le contenu aux informations de contact pertinentes
- Ne pas inclure d'éléments de titre (`<h1>` à `<h6>`) ou de section (`<article>`, `<section>`, etc.) à l'intérieur
- Éviter d'utiliser `<address>` pour des adresses non liées aux contacts du site ou de l'auteur
- Assurer une structure cohérente du document en plaçant `<address>` de manière appropriée

## Accessibilité avancée

### Utilisation d'ARIA pour améliorer la sémantique

```html
<address aria-label="Coordonnées de l'entreprise">
  Société Example<br>
  Tél : <a href="tel:+33123456789">01 23 45 67 89</a>
</address>
```

## Navigation au clavier

L'élément `<address>` n'a pas d'impact direct sur la navigation au clavier. Cependant, assurez-vous que les liens éventuels à l'intérieur sont accessibles au clavier.

## Checklist pour l'audit d'accessibilité

1. Vérifier que `<address>` est utilisé uniquement pour les informations de contact pertinentes
2. S'assurer que le contenu est limité aux coordonnées et n'inclut pas d'éléments de structure inappropriés
3. Contrôler le placement correct de `<address>` dans la structure du document
4. Vérifier l'accessibilité des liens éventuels à l'intérieur de `<address>`

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs à la structure de l'information (thématique 9)
2. Respect des niveaux de conformité visés (A, AA, AAA)
3. Documentation des non-conformités éventuelles et des solutions proposées

### Outils et méthodes

1. Inspection visuelle du code HTML pour vérifier l'utilisation correcte de `<address>`
2. Utilisation d'outils de validation d'accessibilité automatisés
3. Test avec différents lecteurs d'écran pour vérifier la restitution des informations de contact
4. Vérification de l'affichage et du comportement sur différents navigateurs et appareils

En suivant ces recommandations, vous vous assurez que vos éléments `<address>` sont accessibles et conformes aux normes WCAG et RGAA, offrant ainsi une expérience inclusive pour tous les utilisateurs.
