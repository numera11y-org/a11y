# Élément `<button>` accessible

## Principes généraux

Les boutons permettent de soumettre des formulaires ou d'effectuer des actions. Ils doivent être clairement identifiables et accessibles.

## Exemple typique

```html
<button type="submit">Envoyer</button>
```

## Bonnes pratiques

- Utilisez des textes descriptifs pour indiquer l'action du bouton.
- Fournissez des alternatives textuelles si le bouton contient uniquement une icône.

## Accessibilité avancée

- **Bouton avec icône :** Ajoutez un texte caché pour les lecteurs d'écran.

### Exemple

```html
<button>
  <span class="visually-hidden">Rechercher</span>
  <svg role="img" aria-label="Icône de recherche">
    <!-- Contenu SVG -->
  </svg>
</button>

<style>
  .visually-hidden {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
  }
</style>
```

