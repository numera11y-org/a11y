# Élément `<blockquote>` accessible en HTML

## Principes généraux

Pour rendre un `<blockquote>` accessible, il faut respecter ces principes :

- Utiliser la balise pour son usage sémantique, pas pour l'indentation
- Fournir la source de la citation si possible
- Assurer une structure lisible pour les technologies d'assistance
- Maintenir un contraste suffisant avec le texte environnant

## Exemple typique

```html
<blockquote>
  <p>La vie, c'est comme une bicyclette, il faut avancer pour ne pas perdre l'équilibre.</p>
  <footer>— <cite>Albert Einstein</cite></footer>
</blockquote>
```

## Utilisation avancée

### Citation avec source

```html
<blockquote cite="https://example.com/discours-complet">
  <p>Nous choisirons de croire en nos rêves plutôt qu'en nos peurs.</p>
  <footer>
    — <cite>Nelson Mandela</cite>, 
    <a href="https://example.com/discours-complet">Discours d'investiture (1994)</a>
  </footer>
</blockquote>
```

### Citation en langue étrangère

```html
<blockquote lang="en">
  <p>To be or not to be, that is the question.</p>
  <footer>— <cite>William Shakespeare, Hamlet</cite></footer>
</blockquote>
```

## Bonnes pratiques

- Utilisez `<blockquote>` uniquement pour de vraies citations, pas pour l'indentation
- Incluez la source avec l'attribut `cite` quand elle est connue
- Utilisez `<footer>` et `<cite>` pour structurer la source de la citation
- Assurez-vous que la citation est visuellement distincte du texte environnant

## Accessibilité avancée

### Utilisation de l'attribut `cite`

```html
<blockquote cite="https://example.com/source-de-la-citation">
  <p>Le texte de la citation...</p>
</blockquote>
```

### Indication visuelle de la citation

```html
<blockquote class="styled-quote">
  <p>Le texte de la citation...</p>
</blockquote>

<style>
  .styled-quote {
    border-left: 4px solid #ccc;
    padding-left: 1em;
    font-style: italic;
  }
</style>
```

## Navigation au clavier

Les `<blockquote>` ne nécessitent pas de navigation spécifique au clavier, mais assurez-vous que tout lien inclus dans la citation soit accessible au clavier.

## Checklist pour l'audit d'accessibilité des blockquotes

1. Utilisation sémantique correcte de `<blockquote>`
2. Présence de l'attribut `cite` avec une URL valide si applicable
3. Structure appropriée avec `<p>`, `<footer>`, et `<cite>` si nécessaire
4. Contraste suffisant entre la citation et le texte environnant
5. Vérification de l'accessibilité des liens éventuels dans la citation
6. Utilisation correcte de l'attribut `lang` pour les citations en langue étrangère

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs à la structure de l'information (thématique 9)
2. Respect des niveaux de conformité visés (A, AA, AAA)
3. Documentation des non-conformités éventuelles et des solutions proposées

### Outils et méthodes

1. Inspection visuelle des `<blockquote>` pour vérifier leur distinction du texte environnant
2. Utilisation d'outils d'inspection du code pour vérifier la structure HTML
3. Test avec des lecteurs d'écran pour s'assurer que les citations sont correctement annoncées
4. Vérification du contraste des citations avec des outils dédiés
