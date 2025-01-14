# Guide d’implémentation d’un panneau d’information accessible

## Introduction

Les panneaux d'information sont utilisés pour afficher des messages importants ou des notifications aux utilisateurs. Assurer leur accessibilité garantit que tous les utilisateurs, y compris ceux utilisant des technologies d’assistance, peuvent accéder à ces informations de manière efficace.

**Démo :** [CodePen](https://codepen.io/numera11y/pen/NPKYMwm)

## Description technique

### Structure HTML accessible

La structure HTML doit être sémantique et inclure des attributs ARIA pour une meilleure compréhension par les technologies d’assistance.

- **Conteneur du Panneau (`<div>` ou `<section>`) :** Utilisé pour regrouper le contenu du panneau.
- **Attributs ARIA :**
  - `role="alert"` : Indique qu'il s'agit d'un message important nécessitant l'attention immédiate de l'utilisateur.
  - `aria-live="assertive"` : Informe les technologies d’assistance que le contenu doit être annoncé immédiatement.
  - `aria-labelledby` : Associe le panneau à un titre descriptif.

### Comportement javascript accessible

- **Affichage Dynamique :** Si le panneau est affiché ou mis à jour dynamiquement, s'assurer que les attributs ARIA sont correctement mis en place pour notifier les utilisateurs des changements.
- **Fermeture du Panneau :** Si le panneau peut être fermé par l'utilisateur, fournir un bouton avec un `aria-label` explicite, tel que "Fermer l'alerte".

## Bonnes pratiques d’accessibilité

- **Respect des Standards :**
  - Suivre les directives WCAG 2.1, notamment le critère 4.1.3 sur les messages d'état.
- **Messages Visuels et Auditifs :**
  - Assurer que le panneau est visuellement distinct et facilement identifiable.
  - Utiliser des couleurs et des icônes appropriées pour transmettre l'importance du message.
- **Compatibilité Multi-Appareils :**
  - Tester le panneau sur différents appareils et navigateurs pour garantir une expérience uniforme.

## Recommandations supplémentaires

- **Amélioration de l’Expérience Utilisateur :**
  - Fournir des options pour que l'utilisateur puisse interagir avec le panneau, comme le masquer ou en savoir plus.
  - Assurer que le panneau n'obstrue pas le contenu principal et qu'il est facilement navigable au clavier.

## Exemple de code accessible

```html
<div role="alert" aria-live="assertive" aria-labelledby="infoPanelTitle" id="infoPanel">
  <h2 id="infoPanelTitle">Mise à jour importante</h2>
  <p>Nous avons mis à jour nos conditions d'utilisation. Veuillez les lire attentivement.</p>
  <button aria-label="Fermer l'alerte" onclick="closeInfoPanel()">Fermer</button>
</div>

<script>
  function closeInfoPanel() {
    const infoPanel = document.getElementById('infoPanel');
    infoPanel.style.display = 'none';
  }
</script>
```
