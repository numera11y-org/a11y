# Guide d’implémentation d’un darkmode accessible

## Introduction

Permettre aux utilisateurs de basculer entre les modes clair et sombre améliore l'expérience utilisateur en s'adaptant à leurs préférences et à leur confort visuel. Assurer que ce sélecteur est accessible garantit une utilisation fluide pour tous, y compris les personnes utilisant des technologies d’assistance.

**Démo :** [CodePen](https://codepen.io/numera11y/pen/dPbmJQm)

## Description technique

### Structure HTML accessible

La structure HTML doit être sémantique et inclure des attributs ARIA pour une meilleure compréhension par les technologies d’assistance.

- **Bouton (`<button>`) :** Utilisé pour déclencher le changement de mode.
- **Attributs ARIA :**
  - `aria-label` pour décrire l'action du bouton, par exemple, "Activer le mode sombre" ou "Activer le mode clair".
  - `aria-live="polite"` sur un élément contenant le nom du mode actuel pour informer les utilisateurs des changements.

### Comportement javascript accessible

- **Gestion des Événements :** Le bouton doit écouter les événements de clic pour basculer entre les modes.
- **Mise à Jour des Attributs ARIA :** Mettre à jour dynamiquement le `aria-label` du bouton en fonction du mode actif.
- **Stockage des Préférences :** Utiliser le `localStorage` pour mémoriser la préférence de l'utilisateur et appliquer le mode choisi lors des visites ultérieures.

## Bonnes pratiques d’accessibilité

- **Respect des standards :**
  - Suivre les directives WCAG 2.1, notamment le critère 1.4.3 sur le contraste des couleurs.
- **Messages visuels et auditifs :**
  - Fournir des retours visuels clairs lors du changement de mode, comme une transition douce entre les thèmes.
- **Compatibilité multi-appareils :**
  - Tester le sélecteur sur différents appareils et navigateurs pour garantir une expérience uniforme.

## Recommandations supplémentaires

- **Amélioration de l’expérience utilisateur :**
  - Ajouter des transitions CSS pour adoucir le changement de mode.
  - Permettre la détection automatique du mode préféré de l'utilisateur via le media query `prefers-color-scheme`.

## Exemple de code accessible

```html
<button id="mode-toggle" aria-label="Activer le mode sombre">Changer de mode</button>

<script>
  const toggleButton = document.getElementById('mode-toggle');
  const currentMode = localStorage.getItem('color-mode') || 'light';

  document.body.classList.add(currentMode);

  toggleButton.setAttribute('aria-label', currentMode === 'light' ? 'Activer le mode sombre' : 'Activer le mode clair');

  toggleButton.addEventListener('click', () => {
    const newMode = document.body.classList.contains('light') ? 'dark' : 'light';
    document.body.classList.remove('light', 'dark');
    document.body.classList.add(newMode);
    localStorage.setItem('color-mode', newMode);
    toggleButton.setAttribute('aria-label', newMode === 'light' ? 'Activer le mode sombre' : 'Activer le mode clair');
  });
</script>

<style>
  body.light {
    background-color: #ffffff;
    color: #000000;
  }
  body.dark {
    background-color: #000000;
    color: #ffffff;
  }
  button {
    margin: 20px;
    padding: 10px 20px;
    cursor: pointer;
  }
</style>
```
