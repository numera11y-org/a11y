# Guide d’Implémentation d’une Pagination Accessible

## Introduction

La pagination est une composante essentielle des interfaces utilisateur, permettant de naviguer entre différentes pages de contenu. Assurer son accessibilité est crucial pour offrir une expérience utilisateur inclusive, notamment pour les personnes utilisant des technologies d’assistance.

**Démo :** [CodePen](https://codepen.io/numera11y/pen/GgKxQXg)

## Description Technique

### Structure HTML Accessible

La structure HTML de la pagination doit être sémantique et inclure des attributs ARIA pour une meilleure compréhension par les technologies d’assistance.

- **Liste Non Ordonnée (****`<ul>`****) :** Utilisée pour regrouper les éléments de pagination.

- **Éléments de Liste (****`<li>`****) :** Chaque élément représente une page ou une action (précédent, suivant).

- **Liens (****`<a>`****) :** Contenus dans les éléments de liste, ils permettent la navigation entre les pages et incluent des attributs tels que `aria-label` pour décrire leur fonction.

- **Utilisation des rôles ARIA :**

  - `aria-label` sur l’élément `<nav>` pour décrire la navigation.
  - `aria-current="page"` pour indiquer la page active.

- **Assistance à la Navigation Clavier :**

  - Les liens sont naturellement focusables avec le clavier.
  - Assurez-vous que l’ordre des éléments dans le DOM correspond à l’ordre visuel pour une navigation intuitive.

### Comportement JavaScript Accessible

- **Mise à Jour Dynamique :** Lorsqu'une nouvelle page est chargée via JavaScript, déplacez le focus vers une zone pertinente, comme le début du nouveau contenu, pour informer l'utilisateur.

- **Gestion des Attributs ARIA :** Mettez à jour les attributs ARIA pour refléter l'état actuel de la pagination, comme en appliquant `aria-current="page"` au lien correspondant.

## Bonnes Pratiques d’Accessibilité

- **Respect des Standards :**

  - Conformez-vous aux critères WCAG 2.1, notamment le critère 2.4.4 (Navigation cohérente).

- **Messages Visuels et Auditifs :**

  - Fournissez des indications claires sur la page active par des styles visuels distincts et des attributs ARIA appropriés.

- **Compatibilité Multi-Appareils :**

  - Testez la pagination sur différents appareils (ordinateurs, mobiles, tablettes) et technologies d’assistance.

## Recommandations Supplémentaires

- **Amélioration de l’Expérience Utilisateur :**
  - Ajoutez des raccourcis clavier pour naviguer rapidement entre les pages.

## Exemple de Code Accessible

```html
<nav aria-label="Pagination">
  <ul>
    <li><a href="#" aria-label="Page précédente">&laquo;</a></li>
    <li><a href="#" aria-label="Page 1" aria-current="page">1</a></li>
    <li><a href="#" aria-label="Page 2">2</a></li>
    <li><a href="#" aria-label="Page suivante">&raquo;</a></li>
  </ul>
</nav>

<script>
  document.querySelectorAll('nav[aria-label="Pagination"] a').forEach(link => {
    link.addEventListener('click', (event) => {
      event.preventDefault();
      // Logique pour charger le contenu de la page
      // Mettre à jour l'état de la pagination
      document.querySelectorAll('nav[aria-label="Pagination"] a').forEach(l => l.removeAttribute('aria-current'));
      link.setAttribute('aria-current', 'page');
      // Déplacer le focus vers le début du nouveau contenu
      document.getElementById('nouveau-contenu').focus();
    });
  });
</script>
```
