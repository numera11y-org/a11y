## Élément `<fieldset>` accessible

### Principes généraux

L'élément `<fieldset>` est utilisé pour regrouper logiquement des champs de formulaire reliés, tout en fournissant un contexte clair.

### Exemple typique

```html
<fieldset>
  <legend>Informations personnelles</legend>
  <label for="nom">Nom :</label>
  <input type="text" id="nom" name="nom" required>
</fieldset>
```

### Bonnes pratiques

- Utilisez un `<legend>` clair et descriptif.
- Limitez chaque `<fieldset>` à un seul groupe logique de champs.

### Accessibilité avancée

- Fournissez un `aria-describedby` si des instructions supplémentaires sont requises pour l'ensemble des champs.

#### Exemple

```html
<fieldset aria-describedby="group-info">
  <legend>Coordonnées</legend>
  <p id="group-info">Veuillez remplir vos informations personnelles.</p>
  <label for="email">E-mail :</label>
  <input type="email" id="email" name="email" required>
</fieldset>
```

