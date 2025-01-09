# Élément `<dialog>` accessible en HTML

## Principes généraux

Pour rendre un élément `<dialog>` accessible, il faut respecter ces principes :

- Fournir un contenu clair et structuré
- Assurer la navigation au clavier
- Gérer correctement le focus
- Utiliser les attributs ARIA appropriés
- Offrir des moyens de fermer la boîte de dialogue

## Exemple typique

```html
<dialog id="ma-boite-dialogue">
  <h2>Titre de la boîte de dialogue</h2>
  <p>Contenu de la boîte de dialogue</p>
  <button autofocus>OK</button>
  <button>Annuler</button>
</dialog>
```

## Utilisation avancée

### Ouverture et fermeture programmatique

```html
<button id="ouvrir-dialogue">Ouvrir la boîte de dialogue</button>

<dialog id="ma-boite-dialogue">
  <h2>Confirmation</h2>
  <p>Êtes-vous sûr de vouloir continuer ?</p>
  <button id="confirmer">Confirmer</button>
  <button id="annuler">Annuler</button>
</dialog>

<script>
  const dialog = document.getElementById('ma-boite-dialogue');
  const ouvrirBtn = document.getElementById('ouvrir-dialogue');
  const confirmerBtn = document.getElementById('confirmer');
  const annulerBtn = document.getElementById('annuler');

  ouvrirBtn.addEventListener('click', () => {
    dialog.showModal();
  });

  confirmerBtn.addEventListener('click', () => {
    dialog.close('confirm');
  });

  annulerBtn.addEventListener('click', () => {
    dialog.close('cancel');
  });
</script>
```

### Gestion du focus

```javascript
dialog.addEventListener('close', () => {
  ouvrirBtn.focus();
});
```

## Bonnes pratiques

- Utilisez `role="dialog"` ou `role="alertdialog"` si le navigateur ne supporte pas nativement `<dialog>`
- Assurez-vous que le focus est correctement géré à l'ouverture et à la fermeture
- Fournissez toujours un moyen de fermer la boîte de dialogue (bouton de fermeture, touche Échap)
- Utilisez `autofocus` sur le premier élément interactif de la boîte de dialogue

## Accessibilité avancée

### Utilisation de `aria-labelledby` et `aria-describedby`

```html
<dialog id="ma-boite-dialogue" aria-labelledby="dialogue-titre" aria-describedby="dialogue-description">
  <h2 id="dialogue-titre">Confirmation de commande</h2>
  <p id="dialogue-description">Votre commande est prête à être validée. Veuillez confirmer ou annuler.</p>
  <button>Confirmer</button>
  <button>Annuler</button>
</dialog>
```

### Gestion de l'arrière-plan

```css
dialog::backdrop {
  background-color: rgba(0, 0, 0, 0.5);
}
```

## Checklist pour l'audit d'accessibilité des éléments Dialog

1. Vérification de la prise en charge du navigateur et utilisation de polyfills si nécessaire
2. Présence d'un titre clair (`<h2>` ou équivalent)
3. Gestion correcte du focus à l'ouverture et à la fermeture
4. Possibilité de fermer la boîte de dialogue avec la touche Échap
5. Utilisation appropriée des attributs ARIA (`aria-labelledby`, `aria-describedby`)
6. Contraste suffisant entre le contenu et l'arrière-plan
7. Vérification de la navigation au clavier à l'intérieur de la boîte de dialogue
8. Test avec des lecteurs d'écran

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux contenus additionnels apparaissant au survol ou à la prise de focus
2. Respect des niveaux de conformité visés (A, AA, AAA)
3. Documentation des non-conformités éventuelles et des solutions proposées

### Outils et méthodes

1. Test avec différents navigateurs et technologies d'assistance
2. Utilisation d'outils d'inspection d'accessibilité
3. Tests manuels de navigation au clavier
4. Vérification du comportement sur différents appareils (desktop, mobile, tablette)

En suivant ces recommandations, vous vous assurez que vos éléments `<dialog>` sont accessibles et conformes aux normes WCAG et RGAA, offrant ainsi une expérience utilisateur inclusive pour tous, y compris les personnes utilisant des technologies d'assistance.
