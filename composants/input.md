# Élément `<input>` accessible

## Principes généraux

L'élément `<input>` permet la saisie de données et doit être correctement configuré pour assurer une accessibilité optimale :

- Associer chaque champ à une étiquette descriptive via `<label>`.
- Utiliser les attributs appropriés (`required`, `aria-describedby`, `aria-invalid`) pour indiquer l'état et les exigences.

## Exemple typique

```html
<label for="numero">Numéro de téléphone :</label>
<input type="tel" id="numero" name="numero" required aria-describedby="numero-help">
<p id="numero-help">Votre numéro doit être au format international.</p>
```

## Accessibilité avancée

- **Validation dynamique :** Ajoutez `aria-invalid="true"` pour signaler une erreur.
- **Instructions supplémentaires :** Utilisez `aria-describedby` pour fournir des informations contextuelles.

### Exemple

```html
<div>
  <label for="email">Adresse e-mail :</label>
  <input type="email" id="email" name="email" required aria-describedby="email-help" aria-invalid="false">
  <p id="email-help">Veuillez entrer une adresse e-mail valide.</p>
</div>
```

