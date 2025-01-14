# Guide d’accessibilité : filtrage de liste avec support pour lecteurs d’écran

## Introduction

Ce guide présente la mise en œuvre d'un composant de filtrage de liste accessible, permettant aux utilisateurs de rechercher et de filtrer des éléments en temps réel. L'objectif est de garantir une accessibilité optimale pour tous les utilisateurs, y compris ceux utilisant des technologies d'assistance comme les lecteurs d'écran.

**Démo :** [Filtrage de Liste Accessible](https://codepen.io/numera11y/pen/RNbMMYp)

## Description technique

### Structure HTML

La structure HTML du composant suit une approche sémantique pour assurer une accessibilité optimale. Les éléments essentiels incluent :
- Un champ de saisie associé à une étiquette descriptive.
- Une liste non ordonnée contenant les éléments à filtrer.
- Des attributs ARIA permettant d'améliorer la compréhension pour les lecteurs d'écran.

#### Points clés :
- **Utilisation des rôles ARIA :**
  Des attributs tels que `aria-describedby` sont utilisés pour fournir des descriptions supplémentaires et enrichir l'expérience des utilisateurs de lecteurs d'écran.

- **Assistance à la Navigation Clavier :**
  Tous les éléments interactifs sont naturellement accessibles au clavier, garantissant une navigation fluide pour tous les utilisateurs.

### Comportement javascript

JavaScript gère la logique dynamique du filtrage, mettant à jour l'affichage des éléments de la liste en fonction des saisies de l'utilisateur.

#### Points clés :
- Les modifications dynamiques dans le DOM sont immédiatement reflétées, permettant aux lecteurs d'écran de détecter et d'annoncer les changements.
- L'implémentation reste simple et légère, tout en respectant les bonnes pratiques d'accessibilité.

## Bonnes pratiques d’accessibilité

- **Respect des Standards :**
  Le composant est conforme aux normes WCAG 2.1, avec une attention particulière à la navigation au clavier et à la compatibilité avec les lecteurs d'écran.

- **Messages Visuels et Auditifs :**
  Des retours clairs sont fournis via des messages visibles ou audibles, permettant à tous les utilisateurs de comprendre les modifications effectuées.

- **Compatibilité Multi-Appareils :**
  Le composant est testé sur plusieurs plateformes et navigateurs pour garantir une expérience cohérente et sans friction.

## Recommandations supplémentaires

- **Amélioration de l’Expérience Utilisateur :**
  Des fonctionnalités supplémentaires, comme un compteur d'éléments filtrés ou des animations visuelles, peuvent être intégrées tout en restant accessibles.

## Exemple de code accessible

```html
<!-- Exemple HTML -->
<label for="search">Rechercher :</label>
<input type="text" id="search" aria-describedby="search-desc" />
<p id="search-desc">Tapez pour filtrer les éléments affichés dans la liste.</p>

<ul id="item-list">
  <li>Élément 1</li>
  <li>Élément 2</li>
  <li>Élément 3</li>
</ul>
```

```javascript
// Exemple JavaScript
const searchInput = document.getElementById('search');
const items = document.querySelectorAll('#item-list li');

searchInput.addEventListener('input', () => {
  const filter = searchInput.value.toLowerCase();
  items.forEach(item => {
    item.style.display = item.textContent.toLowerCase().includes(filter) ? '' : 'none';
  });
});
```
