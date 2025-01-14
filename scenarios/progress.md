# Guide d’implémentation d’une barre de progression accessible

## Introduction

Les barres de progression sont couramment utilisées pour indiquer l'avancement d'une tâche ou d'un processus. Assurer leur accessibilité est essentiel pour que tous les utilisateurs, y compris ceux utilisant des technologies d’assistance, puissent comprendre l'état d'avancement.

**Démo :** [CodePen](https://codepen.io/numera11y/pen/emOrBjG)

## Description technique

### Structure HTML accessible

La structure HTML doit être sémantique et inclure des attributs ARIA pour une meilleure compréhension par les technologies d’assistance.

- **Élément de Progression (`<div>` avec `role="progressbar"`) :** Représente visuellement la progression.
- **Attributs ARIA :**
  - `aria-valuenow` : Indique la valeur actuelle de la progression.
  - `aria-valuemin` et `aria-valuemax` : Définissent les valeurs minimale et maximale de la progression.
  - `aria-label` ou `aria-labelledby` : Fournissent une description accessible de la barre de progression.

### Comportement javascript accessible

- **Mise à Jour Dynamique :** Mettre à jour les attributs ARIA en temps réel pour refléter l'état actuel de la progression.
- **Notifications aux Utilisateurs :** Utiliser des techniques comme `aria-live` pour informer les utilisateurs des mises à jour importantes sans perturber leur expérience.

## Bonnes pratiques d’accessibilité

- **Respect des Standards :**
  - Suivre les directives WCAG 2.1, notamment le critère 4.1.2 sur les propriétés et états du nom.
- **Messages Visuels et Auditifs :**
  - Assurer que les changements de progression sont annoncés de manière appropriée aux utilisateurs de technologies d’assistance.
- **Compatibilité Multi-Appareils :**
  - Tester la barre de progression sur différents appareils et navigateurs pour garantir une expérience uniforme.

## Recommandations supplémentaires

- **Amélioration de l’Expérience Utilisateur :**
  - Ajouter des indications textuelles supplémentaires, comme un pourcentage, pour fournir plus de contexte aux utilisateurs.
  - Assurer que la barre de progression est visible et contrastée pour les utilisateurs malvoyants.

## Exemple de code accessible

```html
<div id="progressbar" role="progressbar" aria-valuemin="0" aria-valuemax="100" aria-valuenow="0" aria-label="Progression de la tâche">
  <div id="progress" style="width: 0%;"></div>
</div>

<script>
  function updateProgress(value) {
    const progressBar = document.getElementById('progressbar');
    const progress = document.getElementById('progress');
    if (value >= 0 && value <= 100) {
      progress.style.width = value + '%';
      progressBar.setAttribute('aria-valuenow', value);
    }
  }

  // Exemple de mise à jour de la progression
  let currentValue = 0;
  const interval = setInterval(() => {
    if (currentValue < 100) {
      currentValue += 10;
      updateProgress(currentValue);
    } else {
      clearInterval(interval);
    }
  }, 1000);
</script>
```
