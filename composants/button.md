# Élément `<button>` en HTML accessible

## Principes généraux

Pour rendre un élément `<button>` accessible, il faut respecter ces principes :

- Utiliser la balise native `<button>` plutôt que des alternatives non sémantiques comme `<div>` ou `<span>` pour bénéficier de son comportement par défaut.
- Fournir un texte descriptif à l'intérieur du bouton ou via un attribut `aria-label` ou `aria-labelledby`.
- S'assurer que les boutons sont facilement détectables visuellement (contraste suffisant, taille adéquate).
- Garantir que le bouton est utilisable au clavier (focus visible, activable avec la touche Entrée ou Espace).

## Exemple typique

```html
<button>Envoyer</button>
```

## Utilisation avancée

### Bouton avec icône uniquement

```html
<button aria-label="Envoyer">
  <svg aria-hidden="true" focusable="false" width="16" height="16">
    <use href="#icon-send"></use>
  </svg>
</button>
```

### Bouton désactivé

```html
<button disabled>Envoyer</button>
```

## Bonnes pratiques

- Toujours inclure un texte ou une alternative accessible (`aria-label`).
- Éviter d’utiliser `disabled` pour masquer des boutons importants sans fournir une alternative ou une explication.
- Utiliser des styles CSS pour indiquer visuellement les états (focus, actif, désactivé).
- Tester les boutons dans différents navigateurs et avec diverses technologies d’assistance.

## Accessibilité avancée

### Gestion des états avec `aria`

```html
<button aria-pressed="false" onclick="togglePressed(this)">J’aime</button>

<script>
  function togglePressed(button) {
    const isPressed = button.getAttribute("aria-pressed") === "true";
    button.setAttribute("aria-pressed", !isPressed);
  }
</script>
```

### Bouton personnalisé avec comportement natif

```html
<div role="button" tabindex="0" onclick="alert('Action !')" onkeydown="if(event.key==='Enter'||event.key===' ')alert('Action !')">
  Action personnalisée
</div>
```

## Navigation au clavier

Les boutons natifs sont accessibles au clavier sans effort supplémentaire. Les utilisateurs peuvent :

- Naviguer avec la touche Tab.
- Activer un bouton avec Entrée ou Espace.

Si un style personnalisé est appliqué, il est essentiel de garantir un focus visible.

```css
button:focus {
  outline: 2px solid blue;
}
```

## Checklist pour l'audit d'accessibilité

1. Le bouton est-il sémantique (balise `<button>` ou rôle explicite) ?
2. Un texte ou une alternative est-il fourni pour les boutons uniquement graphiques ?
3. Les boutons sont-ils utilisables avec le clavier (Tab, Entrée, Espace) ?
4. Le contraste entre le texte du bouton et son arrière-plan est-il suffisant (minimum 4,5:1) ?
5. Le focus est-il visible lorsque le bouton est activé ?

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux boutons (thématique "Formulaires et éléments interactifs").
2. Respect des niveaux de conformité visés (A, AA, AAA).
3. Documentation des non-conformités éventuelles et des solutions proposées.

### Outils et méthodes

1. Utiliser des extensions de navigateur comme Axe ou Wave pour analyser l’accessibilité.
2. Tester avec un lecteur d’écran (NVDA, JAWS, VoiceOver).
3. Valider la conformité au RGAA et aux WCAG avec des outils comme Tanaguru ou Asqatasun.
