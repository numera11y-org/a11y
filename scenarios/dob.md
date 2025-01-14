# Guide d’implémentation d’un champ de date de naissance accessible

## Introduction

La collecte de la date de naissance est courante dans les formulaires en ligne. Assurer que ce champ est accessible permet à tous les utilisateurs, y compris ceux utilisant des technologies d’assistance, de le remplir facilement et sans confusion.

**Démo :** [CodePen](https://codepen.io/numera11y/pen/wBwmpPN)

## Description technique

### Structure HTML accessible

La structure HTML doit être sémantique et inclure des attributs ARIA pour une meilleure compréhension par les technologies d’assistance.

- **Étiquette (`<label>`) :** Associée à chaque champ de saisie pour indiquer son objectif.
- **Champs de saisie (`<input>`) :** Utilisés pour la saisie du jour, du mois et de l'année.
- **Attributs ARIA et propriétés :**
  - `aria-labelledby` pour lier les champs à leurs étiquettes respectives.
  - `aria-required="true"` pour indiquer que la saisie est obligatoire.
  - Utilisation de `type="number"` pour chaque champ afin de guider l'utilisateur dans le format attendu.

### Comportement javascript accessible

- **Validation en Temps Réel :** Fournir des retours immédiats sur la validité des entrées sans perturber l'utilisateur.
- **Gestion des Erreurs :** Informer clairement l'utilisateur en cas d'erreur, en utilisant des messages textuels associés aux champs concernés.
- **Navigation au Clavier :** Permettre une navigation fluide entre les champs en respectant l'ordre logique de la date (jour, mois, année).

## Bonnes pratiques d’accessibilité

- **Respect des standards :**
  - Suivre les directives WCAG 2.1, notamment le critère 3.3.2 sur les étiquettes ou instructions.
- **Messages visuels et auditifs :**
  - Utiliser des messages d'erreur clairs et concis, visibles et audibles pour les technologies d’assistance.
- **Compatibilité multi-appareils :**
  - Tester le formulaire sur différents appareils et navigateurs pour garantir une expérience uniforme.

## Recommandations supplémentaires

- **Amélioration de l’expérience utilisateur :**
  - Proposer des retours visuels pour valider les champs correctement remplis.
  - Fournir des indications claires sur le format attendu directement dans les étiquettes ou via des placeholders.

## Exemple de code accessible

```html
<div class="date-input-group">
  <h2>Date de naissance</h2>
  <p class="hint-text">Par exemple, 31 05 1988</p>

  <div class="date-inputs">
    <div class="input-wrapper">
      <label for="day">Jour</label>
      <input
        type="number"
        id="day"
        name="day"
        inputmode="numeric"
        pattern="[0-9]*"
        min="1"
        max="31"
        placeholder="JJ"
        aria-label="Jour de naissance"
        required>
    </div>

    <div class="input-wrapper">
      <label for="month">Mois</label>
      <input
        type="number"
        id="month"
        name="month"
        inputmode="numeric"
        pattern="[0-9]*"
        min="1"
        max="12"
        placeholder="MM"
        aria-label="Mois de naissance"
        required>
    </div>

    <div class="input-wrapper">
      <label for="year">Année</label>
      <input
        type="number"
        id="year"
        name="year"
        inputmode="numeric"
        pattern="[0-9]*"
        min="1900"
        max="2100"
        placeholder="AAAA"
        aria-label="Année de naissance"
        required>
    </div>
  </div>
</div>
```

