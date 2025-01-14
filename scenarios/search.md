# Guide d’implémentation d’un champ de recherche accessible

## Introduction

Les champs de recherche sont des éléments courants sur les sites web, permettant aux utilisateurs de trouver rapidement des informations. Assurer leur accessibilité est essentiel pour que tous les utilisateurs, y compris ceux utilisant des technologies d’assistance, puissent les utiliser efficacement.

**Démo :** [CodePen](https://codepen.io/numera11y/pen/OPLvQQV)

## Description technique

### Structure HTML accessible

La structure HTML doit être sémantique et inclure des attributs ARIA pour une meilleure compréhension par les technologies d’assistance.

- **Formulaire de Recherche (`<form role="search">`) :** Utilisé pour encapsuler le champ de recherche.
- **Champ de Recherche (`<input type="search">`) :** Utilisé pour la saisie des requêtes de recherche.
- **Étiquette (`<label>`) :** Associée au champ de recherche pour indiquer son objectif.
- **Bouton de Soumission (`<button type="submit">`) :** Permet de soumettre la requête de recherche.

### Comportement javascript accessible

- **Validation en Temps Réel :** Fournir des retours immédiats sur la validité de la requête sans perturber l'utilisateur.
- **Gestion des Suggestions :** Si des suggestions sont proposées, s'assurer qu'elles sont accessibles via le clavier et lisibles par les technologies d’assistance.

## Bonnes pratiques d’accessibilité

- **Respect des Standards :**
  - Suivre les directives WCAG 2.1, notamment le critère 1.3.1 sur l'information et les relations.
- **Messages Visuels et Auditifs :**
  - Utiliser des messages d'erreur clairs et concis, visibles et audibles pour les technologies d’assistance.
- **Compatibilité Multi-Appareils :**
  - Tester le champ de recherche sur différents appareils et navigateurs pour garantir une expérience uniforme.

## Recommandations supplémentaires

- **Amélioration de l’Expérience Utilisateur :**
  - Fournir des indications sur le type de contenu recherché directement dans l'étiquette ou via des placeholders.
  - Assurer que le champ de recherche est facilement repérable sur la page, avec un contraste suffisant et une taille appropriée.

## Exemple de code accessible

```html
<form role="search" aria-label="Recherche sur le site">
  <label for="search-input">Rechercher :</label>
  <input type="search" id="search-input" name="q" placeholder="Entrez votre recherche" aria-required="true">
  <button type="submit">Rechercher</button>
</form>

<script>
  const searchInput = document.getElementById('search-input');

  // Validation du champ de recherche en temps réel
  searchInput.addEventListener('input', () => {
    if (searchInput.value.trim() === '') {
      searchInput.setAttribute('aria-invalid', 'true');
    } else {
      searchInput.setAttribute('aria-invalid', 'false');
    }
  });
</script>
```
