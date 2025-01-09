# Élément `<details>` accessible en HTML

## Principes généraux

L'élément `<details>` crée un widget de divulgation interactif, souvent appelé "accordéon". Pour le rendre accessible, il faut :

- Fournir un résumé clair avec `<summary>`
- Assurer la navigation au clavier
- Utiliser une structure de contenu logique
- Considérer l'utilisation d'attributs ARIA si nécessaire

## Exemple typique

```html
<details>
  <summary>Cliquez pour plus d'informations</summary>
  <p>Contenu détaillé qui s'affiche lorsque l'élément est ouvert.</p>
</details>
```

## Utilisation avancée

### Avec contenu structuré

```html
<details>
  <summary>Nos services</summary>
  <h3>Conception web</h3>
  <p>Nous créons des sites web responsifs et accessibles.</p>
  <h3>Développement d'applications</h3>
  <p>Nous développons des applications mobiles et de bureau.</p>
</details>
```

### État ouvert par défaut

```html
<details open>
  <summary>Informations importantes (ouvert par défaut)</summary>
  <p>Ce contenu est visible dès le chargement de la page.</p>
</details>
```

## Bonnes pratiques

- Utilisez un texte clair et descriptif dans `<summary>`
- Évitez de nicher des éléments `<details>` trop profondément
- Assurez-vous que le contenu dans `<details>` est bien structuré
- Considérez l'utilisation de JavaScript pour une meilleure gestion des états

## Accessibilité avancée

### Utilisation d'attributs ARIA pour plus de contexte

```html
<details>
  <summary aria-expanded="false" aria-controls="section1">
    Détails sur notre politique de confidentialité
  </summary>
  <div id="section1">
    <p>Notre politique de confidentialité explique comment nous utilisons vos données...</p>
  </div>
</details>
```

### Gestion des événements avec JavaScript

```javascript
const details = document.querySelector('details');
details.addEventListener('toggle', (event) => {
  if (event.target.open) {
    console.log('Le contenu est maintenant visible');
    // Mettre à jour aria-expanded si utilisé
    event.target.querySelector('summary').setAttribute('aria-expanded', 'true');
  } else {
    console.log('Le contenu est maintenant caché');
    event.target.querySelector('summary').setAttribute('aria-expanded', 'false');
  }
});
```

# Navigation au clavier pour `<details>` et `<summary>`

- L'élément `<details>` est nativement accessible au clavier sans nécessiter de code JavaScript supplémentaire.

- Les utilisateurs peuvent naviguer jusqu'à l'élément `<summary>` en utilisant la touche Tab.

- Une fois que le focus est sur l'élément `<summary>`, les utilisateurs peuvent :
  - Ouvrir ou fermer le contenu en appuyant sur la touche Espace ou Entrée.
  - Naviguer dans le contenu révélé en utilisant les flèches du clavier une fois qu'il est ouvert.

- Le comportement par défaut permet une utilisation intuitive et conforme aux attentes des utilisateurs de technologies d'assistance.

Ces fonctionnalités de navigation au clavier sont intégrées par défaut dans les navigateurs modernes qui prennent en charge les éléments `<details>` et `<summary>`, ce qui en fait une solution accessible sans nécessiter de code JavaScript complexe pour la gestion du clavier.

## Checklist pour l'audit d'accessibilité des éléments Details

1. Vérification de la présence d'un élément `<summary>` comme premier enfant
2. Texte clair et descriptif dans `<summary>`
3. Contenu bien structuré à l'intérieur de `<details>`
4. Vérification de la navigation au clavier (ouverture/fermeture avec Entrée ou Espace)
5. Test avec des lecteurs d'écran pour s'assurer que l'état ouvert/fermé est annoncé
6. Contraste suffisant pour le texte du `<summary>`
7. Vérification du comportement sur différents navigateurs et appareils

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux contenus additionnels apparaissant au survol ou à la prise de focus
2. Respect des niveaux de conformité visés (A, AA, AAA)
3. Documentation des non-conformités éventuelles et des solutions proposées

### Outils et méthodes

1. Test manuel de l'interaction au clavier et à la souris
2. Utilisation d'outils d'inspection d'accessibilité
3. Tests avec différentes technologies d'assistance
4. Vérification du rendu et du comportement sur divers navigateurs et appareils

En suivant ces recommandations, vous vous assurez que vos éléments `<details>` sont accessibles et conformes aux normes WCAG et RGAA, offrant ainsi une expérience utilisateur inclusive pour tous, y compris les personnes utilisant des technologies d'assistance.
