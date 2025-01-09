## Élément `<p>` accessible

### Principes généraux

L'élément `<p>` sert à regrouper des blocs de texte. Son utilisation correcte contribue à une expérience de lecture fluide :

- Fournir des textes concis et informatifs.
- Assurer un contraste suffisant entre le texte et l'arrière-plan.

### Exemple typique

```html
<p>Ceci est un paragraphe informatif.</p>
```

### Accessibilité avancée

- **Lien avec des éléments :** Utilisez `id` pour associer un paragraphe à d'autres éléments (ex : `aria-describedby`).

#### Exemple

```html
<p id="instruction">Les champs marqués d'un astérisque (*) sont obligatoires.</p>
<form aria-describedby="instruction">
  <!-- Contenu du formulaire -->
</form>
```

