# Élément `<form>` en HTML accessible

## Principes généraux

Pour rendre un élément `<form>` accessible, il faut respecter ces principes :

- Fournir des labels clairs et descriptifs pour chaque champ de formulaire.
- Associer chaque champ à un élément `<label>` ou utiliser les attributs `aria-label` ou `aria-labelledby` pour les champs non textuels.
- S'assurer que le formulaire est navigable au clavier.
- Fournir des messages d’erreur accessibles et clairs, liés aux champs concernés.
- Utiliser des attributs comme `required`, `aria-required`, et `aria-describedby` pour indiquer les champs obligatoires et fournir des explications.

## Exemple typique

```html
<form action="/submit" method="post">
  <label for="username">Nom d'utilisateur :</label>
  <input type="text" id="username" name="username" required />
  
  <label for="password">Mot de passe :</label>
  <input type="password" id="password" name="password" required />
  
  <button type="submit">Se connecter</button>
</form>
```

## Utilisation avancée

### Formulaire avec validation et messages d'erreur

```html
<form action="/submit" method="post" novalidate>
  <label for="email">Adresse email :</label>
  <input type="email" id="email" name="email" required aria-describedby="email-error" />
  <span id="email-error" class="error-message">Entrez une adresse email valide.</span>
  
  <label for="age">Âge :</label>
  <input type="number" id="age" name="age" min="18" max="99" aria-describedby="age-error" />
  <span id="age-error" class="error-message">Âge entre 18 et 99 ans requis.</span>
  
  <button type="submit">Soumettre</button>
</form>
```

### Utilisation avec ARIA pour les groupes de champs

```html
<form>
  <fieldset>
    <legend>Choisissez vos préférences</legend>
    <label>
      <input type="checkbox" name="newsletters" value="daily" />
      Quotidiennes
    </label>
    <label>
      <input type="checkbox" name="newsletters" value="weekly" />
      Hebdomadaires
    </label>
  </fieldset>
  <button type="submit">Valider</button>
</form>
```

## Bonnes pratiques

- Inclure une balise `<label>` explicite pour chaque champ ou utiliser `aria-label` si un label visible n’est pas applicable.
- Structurer le formulaire avec des `<fieldset>` et `<legend>` pour regrouper les champs logiquement liés.
- Fournir un bouton de soumission clair avec un texte explicite, par exemple, "Envoyer" ou "Valider".
- Ajouter des indications pour les champs obligatoires (`required`) ou des contraintes spécifiques (`min`, `max`, `pattern`).
- Inclure des messages d'erreur accessibles et précis liés aux champs concernés.

## Accessibilité avancée

### Champs obligatoires avec indications claires

```html
<form>
  <label for="fullname">Nom complet <span aria-hidden="true">*</span></label>
  <input type="text" id="fullname" name="fullname" required aria-required="true" />
</form>
```

### Validation dynamique avec messages accessibles

```html
<form>
  <label for="username">Nom d'utilisateur :</label>
  <input type="text" id="username" name="username" required aria-describedby="username-error" />
  <span id="username-error" role="alert">Ce champ est obligatoire.</span>
</form>
```

## Navigation au clavier

Les utilisateurs peuvent naviguer dans un formulaire avec :

- **Tab** pour passer d’un champ à l’autre.
- **Maj + Tab** pour revenir au champ précédent.
- **Entrée** pour soumettre le formulaire lorsque le focus est sur un bouton de soumission.

Assurez-vous que le focus est visible et que l’ordre des champs est logique.

## Checklist pour l'audit d'accessibilité

1. Les champs sont correctement associés à leurs labels (`<label>` ou attributs ARIA).
2. Les champs obligatoires sont indiqués clairement (avec `required` ou `aria-required`).
3. Les messages d’erreur sont liés aux champs correspondants et accessibles via les technologies d’assistance.
4. La navigation au clavier est fluide et logique.
5. Le formulaire utilise des groupes logiques pour les champs associés (via `<fieldset>` et `<legend>`).
6. Les champs de formulaire respectent les critères de contraste requis pour les bordures, le texte ou les labels.

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux formulaires.
2. Respect des niveaux de conformité visés (A, AA, AAA).
3. Documentation des non-conformités éventuelles et des solutions proposées.

### Outils et méthodes

1. Utiliser des extensions de navigateur comme Axe ou Wave pour analyser l’accessibilité.
2. Tester avec un lecteur d’écran (NVDA, JAWS, VoiceOver).
3. Valider la conformité au RGAA et aux WCAG avec des outils comme Tanaguru ou Asqatasun.

En suivant ces recommandations, vos éléments `<form>` seront accessibles et conformes aux normes WCAG et RGAA, garantissant une expérience utilisateur inclusive et efficace.
