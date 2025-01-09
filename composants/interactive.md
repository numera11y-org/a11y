# Éléments interactifs avancés

## Barre de progression accessible

## Principes généraux

- Indiquer clairement l'état d'avancement.
- Mettre à jour dynamiquement `aria-valuenow`.

## Bonnes pratiques

- Ajouter un retour visuel avec des couleurs contrastées.
- Fournir un texte alternatif décrivant la progression pour les lecteurs d'écran.

## Accessibilité avancée

- **Mise à jour dynamique :** Fournissez une mise à jour en temps réel avec JavaScript pour garantir que `aria-valuenow` reflète correctement l'état de progression.

### Exemple

```html
<div id="progress" role="progressbar" aria-valuemin="0" aria-valuemax="100" aria-valuenow="50">
  <div style="width: 50%;">50%</div>
</div>

<script>
  let progress = 50;
  const progressBar = document.getElementById('progress');

  setInterval(() => {
    if (progress < 100) {
      progress += 10;
      progressBar.setAttribute('aria-valuenow', progress);
      progressBar.firstElementChild.style.width = `${progress}%`;
      progressBar.firstElementChild.textContent = `${progress}%`;
    }
  }, 1000);
</script>
```

