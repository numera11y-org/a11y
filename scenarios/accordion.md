# Guide d’implémentation d’un Accordéon accessible

## Introduction

Un accordéon est un composant d’interface utilisateur permettant d’afficher ou de masquer du contenu associé à des en-têtes. Ce code met en œuvre un accordéon accessible en utilisant des attributs ARIA et des pratiques modernes d’accessibilité.

**Démo :** [CodePen](https://codepen.io/numera11y/pen/vEBRdMY)

## Description du code

### Structure HTML

- Un conteneur principal utilise l’attribut `role="tablist"` pour regrouper les éléments de l’accordéon.
- Chaque en-tête est un bouton `<button>` avec :
  - `aria-expanded` : indique l’état (développé ou réduit).
  - `aria-controls` : fait référence à l’ID de la section de contenu associée.
- Les sections de contenu sont des `<div>` marquées avec :
  - `role="region"` : indique qu’il s’agit d’une zone de contenu.
  - Un ID correspondant à l’attribut `aria-controls` des boutons.

### Comportement JavaScript

- Les boutons sont configurés avec des écouteurs d’événements `click`.
- L’état de `aria-expanded` est mis à jour dynamiquement pour refléter l’état d’ouverture ou de fermeture.
- La navigation clavier est gérée pour permettre aux utilisateurs d’utiliser les touches fléchées afin de déplacer le focus entre les en-têtes.

## Bonnes pratiques d’accessibilité

- **Attributs ARIA :**

  - Utiliser `role="tablist"` pour le conteneur principal.
  - Associer `aria-expanded` et `aria-controls` pour indiquer l’état et l’association des boutons et des contenus.
  - Marquer les sections de contenu avec `role="region"` pour décrire leur fonction.

- **Gestion des états :**

  - Mettre à jour dynamiquement les attributs ARIA en fonction de l’interaction.

- **Navigation clavier :**

  - Permettre l’utilisation des touches fléchées pour parcourir les en-têtes.

## Recommandations supplémentaires

- **Libellés explicites :**

  - Ajouter des textes descriptifs aux boutons pour améliorer la compréhension du contenu.

- **Transitions fluides :**

  - Intégrer des animations légères pour une meilleure expérience utilisateur.

- **Tests compatibilité :**

  - Tester l’accordéon avec différentes technologies d’assistance (lecteurs d’écran, claviers alternatifs).

## Exemple simplifié

```html
<div role="tablist">
  <button aria-expanded="false" aria-controls="section1">En-tête 1</button>
  <div id="section1" role="region" hidden>
    Contenu de la section 1.
  </div>

  <button aria-expanded="false" aria-controls="section2">En-tête 2</button>
  <div id="section2" role="region" hidden>
    Contenu de la section 2.
  </div>
</div>

<script>
  const buttons = document.querySelectorAll('[aria-controls]');

  buttons.forEach(button => {
    button.addEventListener('click', () => {
      const expanded = button.getAttribute('aria-expanded') === 'true';
      button.setAttribute('aria-expanded', !expanded);
      document.getElementById(button.getAttribute('aria-controls')).hidden = expanded;
    });
  });
</script>
```
