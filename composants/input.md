# Élément `<input>` en HTML accessible

## Principes généraux

Pour rendre un élément `<input>` accessible :

- Associer chaque champ à un `<label>` descriptif via l'attribut `for` ou en entourant le champ avec le label.
- Utiliser les attributs `required`, `aria-required`, `aria-describedby` ou `aria-invalid` pour indiquer des contraintes ou des erreurs.
- Proposer des types spécifiques (`email`, `number`, `date`, etc.) pour que les navigateurs et les lecteurs d'écran puissent optimiser l'expérience utilisateur.
- Veiller à ce que les champs soient navigables au clavier et compatibles avec les technologies d'assistance.

## Exemple typique

```html
<form>
  <label for="username">Nom d'utilisateur :</label>
  <input type="text" id="username" name="username" required />
</form>
```

## Utilisation avancée

### Champs avec des indications supplémentaires

```html
<form>
  <label for="email">Adresse email :</label>
  <input
    type="email"
    id="email"
    name="email"
    aria-describedby="email-hint"
    required
  />
  <span id="email-hint">Veuillez entrer une adresse email valide.</span>
</form>
```

### Champs avec validation dynamique

```html
<form>
  <label for="password">Mot de passe :</label>
  <input
    type="password"
    id="password"
    name="password"
    required
    aria-describedby="password-error"
    aria-invalid="false"
  />
  <span id="password-error" class="error-message" style="display: none;">
    Le mot de passe doit contenir au moins 8 caractères.
  </span>
</form>

<script>
  const passwordInput = document.getElementById('password');
  const errorMessage = document.getElementById('password-error');

  passwordInput.addEventListener('input', () => {
    if (passwordInput.value.length < 8) {
      passwordInput.setAttribute('aria-invalid', 'true');
      errorMessage.style.display = 'block';
    } else {
      passwordInput.setAttribute('aria-invalid', 'false');
      errorMessage.style.display = 'none';
    }
  });
</script>
```

### Champs avec autocomplétion

```html
<form>
  <label for="address">Adresse :</label>
  <input
    type="text"
    id="address"
    name="address"
    autocomplete="street-address"
  />
</form>
```

## Bonnes pratiques

- Toujours associer un champ `<input>` à un label explicite.
- Préférer des types d'entrée spécifiques (`email`, `tel`, `url`) pour tirer parti des validations natives des navigateurs.
- Fournir des indications claires en cas de contraintes spécifiques (longueur minimale, format attendu, etc.).
- Ajouter des messages d’erreur accessibles qui décrivent clairement le problème et comment le résoudre.

## Accessibilité avancée

### Champs obligatoires

```html
<form>
  <label for="fullname">Nom complet :</label>
  <input
    type="text"
    id="fullname"
    name="fullname"
    required
    aria-required="true"
  />
</form>
```

### Champs masqués mais accessibles

```html
<form>
  <label for="hidden-input" class="sr-only">Identifiant caché :</label>
  <input
    type="hidden"
    id="hidden-input"
    name="hidden-input"
    aria-hidden="false"
  />
</form>

<style>
  .sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
  }
</style>
```

## Navigation au clavier

- **Tab** pour naviguer entre les champs.
- **Maj + Tab** pour revenir en arrière.
- **Entrée** ou **Espace** pour activer les boutons ou champs interactifs (comme les cases à cocher ou les boutons radio).

Il est crucial de veiller à ce que l’ordre des champs soit logique pour une navigation fluide.

## Checklist pour l'audit d'accessibilité

1. Chaque champ est associé à un label descriptif (`<label>` ou `aria-label`).
2. Les champs obligatoires sont signalés avec `required` ou `aria-required`.
3. Les erreurs sont signalées avec `aria-invalid` et décrites avec `aria-describedby`.
4. Les champs utilisent des types appropriés pour améliorer la validation et l’expérience utilisateur (`email`, `tel`, etc.).
5. La navigation au clavier est fluide et logique.
6. Les champs respectent les critères de contraste pour leurs bordures, textes et labels.

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux formulaires.
2. Respect des niveaux de conformité visés (A, AA, AAA).
3. Documentation des non-conformités éventuelles et des solutions proposées.

### Outils et méthodes

1. Utiliser des extensions de navigateur comme Axe ou Wave pour analyser l'accessibilité des formulaires.
2. Tester avec un lecteur d’écran (NVDA, JAWS, VoiceOver) pour valider l'expérience utilisateur.
3. Vérifier les contrastes avec des outils comme Colour Contrast Analyser.

En suivant ces recommandations, vos champs `<input>` seront accessibles et conformes aux normes WCAG et RGAA, garantissant une expérience utilisateur inclusive et optimale.
