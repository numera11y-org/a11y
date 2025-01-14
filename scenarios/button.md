# Guide d’implémentation d’un bouton accessible

## Introduction

Les boutons sont des éléments interactifs essentiels dans les interfaces utilisateur. Assurer leur accessibilité garantit que tous les utilisateurs, y compris ceux utilisant des technologies d’assistance, peuvent interagir efficacement avec eux.

**Démo :** [CodePen](https://codepen.io/numera11y/pen/QwLmoMQ)

## Description technique

### Structure HTML accessible

La structure HTML doit être sémantique et inclure des attributs ARIA pour une meilleure compréhension par les technologies d’assistance.

- **Élément bouton (`<button>` ou `<a role="button">`) :** Utilisé pour déclencher une action.
- **Attributs ARIA :**
  - `aria-label` : Fournit une description accessible si le texte du bouton n'est pas suffisamment explicite.
  - `role="button"` : Utilisé sur des éléments non-boutons (comme `<a>`) pour indiquer leur fonction de bouton.

### Comportement javascript accessible

- **Gestion des Événements :** Assurer que les événements associés au bouton sont accessibles via le clavier (par exemple, en écoutant les événements `click` et `keydown`).
- **Focus Visible :** Assurer qu'un indicateur de focus est présent lorsque le bouton est sélectionné via le clavier.

## Bonnes pratiques d’accessibilité

- **Respect des standards :**
  - Suivre les directives WCAG 2.1, notamment le critère 4.1.2 sur les propriétés et états du nom.
- **Messages visuels et auditifs :**
  - Assurer que les actions déclenchées par le bouton fournissent des retours appropriés aux utilisateurs, visibles et audibles pour les technologies d’assistance.
- **Compatibilité multi-appareils :**
  - Tester le bouton sur différents appareils et navigateurs pour garantir une expérience uniforme.

## Recommandations supplémentaires

- **Amélioration de l’expérience utilisateur :**
  - Utiliser des styles visuels clairs pour indiquer l'état du bouton (par exemple, actif, désactivé, survolé).
  - Fournir des retours immédiats lorsque le bouton est activé, comme un changement de texte ou une animation subtile.

## Exemple de code accessible

```html
<button id="accessibleButton" aria-label="Enregistrer les modifications">Enregistrer</button>

<script>
  const button = document.getElementById('accessibleButton');

  button.addEventListener('click', () => {
    // Logique à exécuter lors du clic sur le bouton
    alert('Modifications enregistrées avec succès.');
  });

  button.addEventListener('keydown', (event) => {
    if (event.key === 'Enter' || event.key === ' ') {
      // Empêcher le défilement par défaut lors de l'appui sur la barre d'espace
      event.preventDefault();
      // Simuler un clic lorsque la touche Entrée ou Espace est pressée
      button.click();
    }
  });
</script>
```
