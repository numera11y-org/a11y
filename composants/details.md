# Élément `<details>` en HTML accessible

## Principes généraux

Pour rendre un élément `<details>` accessible, il faut respecter ces principes :

- Utiliser l'élément `<summary>` comme titre descriptif pour fournir un résumé clair du contenu à développer.
- Garantir que le contenu caché dans `<details>` est pertinent et accessible une fois déployé.
- Éviter de masquer des informations critiques uniquement dans `<details>` sans indiquer clairement leur présence.
- Tester l'interaction avec le clavier et les lecteurs d'écran.

## Exemple typique

```html
<details>
  <summary>Informations supplémentaires</summary>
  Voici des informations détaillées sur ce sujet.
</details>
```

## Utilisation avancée

### Contrôle de l'état par défaut

```html
<details open>
  <summary>Informations visibles par défaut</summary>
  Le contenu de ce bloc est visible dès le chargement de la page.
</details>
```

### Utilisation imbriquée

```html
<details>
  <summary>Options avancées</summary>
  <details>
    <summary>Paramètres supplémentaires</summary>
    Contenu des paramètres supplémentaires.
  </details>
</details>
```

## Bonnes pratiques

- Fournir un texte clair et concis pour `<summary>`.
- S'assurer que l'ouverture et la fermeture de `<details>` ne perturbent pas les utilisateurs (pas de focus automatique ou de contenu déplacé brusquement).
- Ajouter une animation douce pour les transitions, si possible, pour améliorer l'expérience utilisateur.
- Tester les comportements sur divers navigateurs et technologies d’assistance.

## Accessibilité avancée

### Fournir des indications supplémentaires

```html
<details>
  <summary>Voir les détails <span aria-hidden="true">(cliquez pour développer)</span></summary>
  Voici les détails de cette section.
</details>
```

### Indiquer visuellement l'état ouvert/fermé

```html
<style>
  summary::after {
    content: " ▶";
  }
  details[open] summary::after {
    content: " ▼";
  }
</style>
<details>
  <summary>Plus d'informations</summary>
  Voici un contenu détaillé.
</details>
```

## Navigation au clavier

Les utilisateurs peuvent naviguer dans un élément `<details>` avec :

- **Tab** pour atteindre `<summary>`.
- **Entrée** ou **Espace** pour ouvrir ou fermer `<details>`.

Si des styles personnalisés sont appliqués, il est important de conserver un focus visible.

```css
summary:focus {
  outline: 2px solid blue;
}
```

## Checklist pour l'audit d'accessibilité

1. Le contenu de `<summary>` est clair et descriptif.
2. Les interactions (ouverture/fermeture) fonctionnent correctement au clavier.
3. Les lecteurs d’écran annoncent correctement l’état (ouvert/fermé).
4. Le contenu à l'intérieur de `<details>` est lisible et structuré.
5. Le focus reste logique après l'ouverture/fermeture de `<details>`.


### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux éléments interactifs.
2. Respect des niveaux de conformité visés (A, AA, AAA).
3. Documentation des non-conformités éventuelles et des solutions proposées.

### Outils et méthodes

1. Utiliser des extensions de navigateur comme Axe ou Wave pour analyser l’accessibilité.
2. Tester avec un lecteur d’écran (NVDA, JAWS, VoiceOver).
3. Valider la conformité au RGAA et aux WCAG avec des outils comme Tanaguru ou Asqatasun.

En suivant ces recommandations, vos éléments `<details>` seront accessibles et conformes aux normes WCAG et RGAA, offrant une expérience inclusive et conviviale pour tous les utilisateurs.
