# Élément `<fieldset>` en HTML accessible

## Principes généraux

Pour rendre un élément `<fieldset>` accessible, il faut respecter ces principes :

- Utiliser `<fieldset>` pour regrouper logiquement des champs de formulaire liés.
- Fournir une description via l'élément `<legend>` pour identifier le groupe de champs.
- Éviter de masquer visuellement le `<legend>` tout en conservant son rôle descriptif pour les technologies d’assistance.
- Tester la navigation et l’interaction au clavier avec les champs regroupés dans le `<fieldset>`.

## Exemple typique

```html
<form>
  <fieldset>
    <legend>Informations personnelles</legend>
    <label for="name">Nom :</label>
    <input type="text" id="name" name="name" />
    <label for="email">Email :</label>
    <input type="email" id="email" name="email" />
  </fieldset>
</form>
```

## Utilisation avancée

### Groupement de champs avec des options multiples

```html
<form>
  <fieldset>
    <legend>Choisissez votre abonnement</legend>
    <label>
      <input type="radio" name="subscription" value="monthly" />
      Mensuel
    </label>
    <label>
      <input type="radio" name="subscription" value="yearly" />
      Annuel
    </label>
  </fieldset>
</form>
```

### Utilisation de styles personnalisés

```html
<style>
  fieldset {
    border: 2px solid #007acc;
    padding: 10px;
  }
  legend {
    font-weight: bold;
  }
</style>
<form>
  <fieldset>
    <legend>Paramètres de notification</legend>
    <label>
      <input type="checkbox" name="email_notifications" />
      Notifications par email
    </label>
    <label>
      <input type="checkbox" name="sms_notifications" />
      Notifications par SMS
    </label>
  </fieldset>
</form>
```

## Bonnes pratiques

- Toujours inclure un `<legend>` pour chaque `<fieldset>` afin de fournir une description claire du groupe de champs.
- Éviter de styliser ou masquer le `<legend>` de manière à le rendre invisible ou inaccessible.
- Regrouper uniquement les champs qui sont logiquement liés dans un même `<fieldset>`.
- Ajouter des explications supplémentaires ou des messages d'erreur à l'intérieur du `<fieldset>` si nécessaire.

## Accessibilité avancée

### Contenu masqué visuellement mais accessible

```html
<fieldset>
  <legend class="sr-only">Informations de livraison</legend>
  <label for="address">Adresse :</label>
  <input type="text" id="address" name="address" />
</fieldset>

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

### Gestion des messages d'erreur

```html
<fieldset>
  <legend>Coordonnées</legend>
  <label for="phone">Numéro de téléphone :</label>
  <input type="tel" id="phone" name="phone" aria-describedby="phone-error" />
  <span id="phone-error" style="color: red;">Numéro de téléphone invalide.</span>
</fieldset>
```

## Navigation au clavier

Les utilisateurs peuvent naviguer dans un `<fieldset>` et ses champs avec :

- **Tab** pour passer d’un champ à l’autre.
- **Maj + Tab** pour revenir au champ précédent.

Le `<legend>` est annoncé par les lecteurs d’écran comme description du groupe, aidant les utilisateurs à comprendre le contexte.

## Checklist pour l'audit d'accessibilité

1. Le `<fieldset>` regroupe logiquement des champs liés.
2. Un `<legend>` est fourni pour identifier chaque groupe de champs.
3. Le `<legend>` est lisible et accessible visuellement et via les technologies d’assistance.
4. Les champs regroupés dans le `<fieldset>` sont accessibles au clavier.
5. Les styles appliqués au `<fieldset>` et au `<legend>` n’altèrent pas leur accessibilité.

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux formulaires et éléments structurants.
2. Respect des niveaux de conformité visés (A, AA, AAA).
3. Documentation des non-conformités éventuelles et des solutions proposées.

### Outils et méthodes

1. Utiliser des extensions de navigateur comme Axe ou Wave pour analyser l’accessibilité.
2. Tester avec un lecteur d’écran (NVDA, JAWS, VoiceOver).
3. Valider la conformité au RGAA et aux WCAG avec des outils comme Tanaguru ou Asqatasun.

En suivant ces recommandations, vos éléments `<fieldset>` seront accessibles et conformes aux normes WCAG et RGAA, offrant une expérience utilisateur inclusive et optimale.
