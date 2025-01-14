# Guide d’implémentation de boutons radio accessibles

## Introduction

Les boutons radio permettent aux utilisateurs de sélectionner une seule option parmi un ensemble. Assurer leur accessibilité est essentiel pour que tous les utilisateurs, y compris ceux utilisant des technologies d’assistance, puissent interagir avec eux de manière efficace.

**Démo :** [CodePen](https://codepen.io/numera11y/pen/WbezMbv)

## Description technique

### Structure HTML accessible

La structure HTML doit être sémantique et inclure des attributs ARIA pour une meilleure compréhension par les technologies d’assistance.

- **Groupe de Boutons Radio (`<fieldset>` et `<legend>`) :** Utilisés pour regrouper logiquement les boutons radio et fournir une légende descriptive.
- **Bouton Radio (`<input type="radio">`) :** Permet la sélection d'une option.
- **Étiquette (`<label>`) :** Associée à chaque bouton radio pour indiquer son objectif.

### Comportement javascript accessible

- **Gestion du Focus :** Assurer que les boutons radio sont focusables et que les utilisateurs peuvent naviguer entre eux en utilisant le clavier.
- **Mise à Jour Dynamique :** Si l'état des boutons radio est modifié via JavaScript, s'assurer que les attributs ARIA sont mis à jour en conséquence.

## Bonnes pratiques d’accessibilité

- **Respect des Standards :**
  - Suivre les directives WCAG 2.1, notamment le critère 1.3.1 sur l'information et les relations.
- **Messages Visuels et Auditifs :**
  - Fournir des retours visuels clairs sur l'état sélectionné des boutons radio.
  - Assurer que les changements d'état sont annoncés par les technologies d’assistance.
- **Compatibilité Multi-Appareils :**
  - Tester les boutons radio sur différents appareils et navigateurs pour garantir une expérience uniforme.

## Recommandations supplémentaires

- **Amélioration de l’Expérience Utilisateur :**
  - Fournir des descriptions supplémentaires si nécessaire pour clarifier l'objectif de chaque bouton radio.
  - Assurer que la zone cliquable est suffisamment grande pour faciliter l'interaction, en incluant l'étiquette associée.

## Exemple de code accessible

```html
<form>
  <fieldset>
    <legend>Choisissez votre couleur préférée :</legend>
    <div>
      <input type="radio" id="colorRed" name="favoriteColor" value="red" aria-checked="false">
      <label for="colorRed">Rouge</label>
    </div>
    <div>
      <input type="radio" id="colorGreen" name="favoriteColor" value="green" aria-checked="false">
      <label for="colorGreen">Vert</label>
    </div>
    <div>
      <input type="radio" id="colorBlue" name="favoriteColor" value="blue" aria-checked="false">
      <label for="colorBlue">Bleu</label>
    </div>
  </fieldset>
  <div id="error-message" style="color: red; display: none;" aria-live="assertive"></div>
  <button type="submit">Soumettre</button>
</form>

<script>
  const radioButtons = document.querySelectorAll('input[type="radio"][name="favoriteColor"]');
  const errorMessage = document.getElementById('error-message');

  // Gestion de l'état des boutons radio
  radioButtons.forEach(radio => {
    radio.addEventListener('change', () => {
      radioButtons.forEach(rb => rb.setAttribute('aria-checked', 'false'));
      if (radio.checked) {
        radio.setAttribute('aria-checked', 'true');
      }
    });
  });

  // Validation du formulaire
  document.querySelector('form').addEventListener('submit', (event) => {
    const isChecked = Array.from(radioButtons).some(radio => radio.checked);
    if (!isChecked) {
      event.preventDefault();
      errorMessage.style.display = 'block';
      errorMessage.textContent = 'Vous devez sélectionner une couleur pour continuer.';
    } else {
      errorMessage.style.display = 'none';
      errorMessage.textContent = '';
    }
  });
</script>
```
