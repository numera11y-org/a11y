# Guide d’implémentation de liens externes accessibles

## Introduction

Les liens externes dirigent les utilisateurs vers des sites ou des ressources en dehors du domaine actuel. Il est essentiel de les rendre accessibles afin que tous les utilisateurs, y compris ceux utilisant des technologies d’assistance, puissent les identifier et les utiliser efficacement.

**Démo :** [CodePen](https://codepen.io/numera11y/pen/JoPLLMj)

## Description technique

### Structure HTML accessible

La structure HTML doit être sémantique et inclure des attributs ARIA pour une meilleure compréhension par les technologies d’assistance.

- **Élément lien (`<a>`) :** Utilisé pour créer des hyperliens vers des ressources externes.
- **Attributs :**
  - `href` : Spécifie l'URL de la ressource externe.
  - `target="_blank"` : Ouvre le lien dans un nouvel onglet ou une nouvelle fenêtre.
  - `rel="noopener noreferrer"` : Améliore la sécurité en empêchant la page référencée d'accéder à `window.opener`.
  - `aria-label` : Fournit une description accessible si le texte du lien n'est pas suffisamment explicite.

### Comportement JavaScript accessible

- **Indication visuelle :** Ajouter des icônes ou des indices visuels pour signaler que le lien ouvre une nouvelle fenêtre ou mène à un site externe.
- **Notifications aux utilisateurs :** Informer les utilisateurs que le lien s'ouvrira dans un nouvel onglet, soit via du texte visible, soit via des attributs ARIA.

## Bonnes pratiques d’accessibilité

- **Respect des standards :**
  - Suivre les directives WCAG 2.1, notamment le critère 2.4.4 sur l'objectif du lien (dans le contexte).
- **Messages visuels et auditifs :**
  - Assurer que les utilisateurs sont informés de l'ouverture d'un nouvel onglet ou d'une nouvelle fenêtre.
- **Compatibilité multi-appareils :**
  - Tester les liens externes sur différents appareils et navigateurs pour garantir une expérience uniforme.

## Recommandations supplémentaires

- **Amélioration de l’expérience utilisateur :**
  - Utiliser des icônes accompagnées de texte pour indiquer les liens externes.
  - Fournir des informations supplémentaires, comme des descriptions ou des aperçus, pour aider les utilisateurs à décider de cliquer sur le lien.

## Exemple de code accessible

```html
<a href="https://www.example.com" target="_blank" rel="noopener noreferrer" aria-label="Visitez Example.com, s'ouvre dans un nouvel onglet">
  Visitez Example.com
  <span aria-hidden="true">🔗</span>
</a>
```
