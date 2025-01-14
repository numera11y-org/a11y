# Guide d’implémentation d’un champ de mot de passe accessible

## Introduction

Les champs de mot de passe sont essentiels pour la sécurité des utilisateurs. Assurer leur accessibilité garantit que tous les utilisateurs, y compris ceux utilisant des technologies d’assistance, peuvent interagir avec ces champs de manière efficace et sécurisée.

**Démo :** [CodePen](https://codepen.io/numera11y/pen/LEPdepx)

## Description technique

### Structure HTML accessible

La structure HTML doit être sémantique et inclure des attributs ARIA pour une meilleure compréhension par les technologies d’assistance.

- **Étiquette (`<label>`) :** Associée au champ de saisie pour indiquer son objectif.
- **Champ de saisie (`<input type="password">`) :** Utilisé pour la saisie du mot de passe.
- **Bouton de visibilité (`<button>`) :** Permet de basculer la visibilité du mot de passe.
- **Attributs ARIA et propriétés :**
  - `aria-label` sur le bouton pour indiquer son action, par exemple, "Afficher le mot de passe" ou "Masquer le mot de passe".
  - `aria-live="polite"` sur un élément contenant des messages d'erreur ou d'information pour informer les utilisateurs des changements.

### Comportement javascript accessible

- **Gestion de la visibilité du mot de passe :** Le bouton doit permettre de basculer entre les modes texte et mot de passe, en mettant à jour l'attribut `type` du champ de saisie.
- **Mise à jour des attributs ARIA :** Mettre à jour dynamiquement le `aria-label` du bouton en fonction de l'état actuel (affiché ou masqué).
- **Validation en Temps Réel :** Fournir des retours immédiats sur la validité du mot de passe sans perturber l'utilisateur.

## Bonnes pratiques d’accessibilité

- **Respect des standards :**
  - Suivre les directives WCAG 2.1, notamment le critère 1.3.1 sur l'information et les relations.
- **Messages visuels et auditifs :**
  - Utiliser des messages d'erreur clairs et concis, visibles et audibles pour les technologies d’assistance.
- **Compatibilité multi-appareils :**
  - Tester le champ de mot de passe sur différents appareils et navigateurs pour garantir une expérience uniforme.

## Recommandations supplémentaires

- **Amélioration de l'expérience utilisateur :**
  - Ajouter des indications sur les critères de complexité du mot de passe requis.
  - Fournir une option pour générer un mot de passe sécurisé automatiquement.

## Exemple de code accessible

```html
<form>
  <label for="password">Mot de passe</label>
  <input type="password" id="password" name="password" aria-describedby="passwordHelp">
  <button type="button" id="togglePassword" aria-label="Afficher le mot de passe">👁️</button>
  <div id="passwordHelp" aria-live="polite">Votre mot de passe doit contenir au moins 8 caractères.</div>
  <div id="error-message" style="color: red; display: none;" aria-live="assertive"></div>
  <button type="submit">Soumettre</button>
</form>

<script>
  const passwordInput = document.getElementById('password');
  const togglePasswordButton = document.getElementById('togglePassword');
  const errorMessage = document.getElementById('error-message');

  // Gestion de la visibilité du mot de passe
  togglePasswordButton.addEventListener('click', () => {
    const type = passwordInput.getAttribute('type') === 'password' ? 'text' : 'password';
    passwordInput.setAttribute('type', type);
    const label = togglePasswordButton.getAttribute('aria-label') === 'Afficher le mot de passe' ? 'Masquer le mot de passe' : 'Afficher le mot de passe';
    togglePasswordButton.setAttribute('aria-label', label);
  });

  // Validation du mot de passe en temps réel
  passwordInput.addEventListener('input', () => {
    if (passwordInput.value.length < 8) {
      errorMessage.style.display = 'block';
      errorMessage.textContent = 'Le mot de passe doit contenir au moins 8 caractères.';
    } else {
      errorMessage.style.display = 'none';
      errorMessage.textContent = '';
    }
  });
</script>
```
