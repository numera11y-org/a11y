# Éléments multimédias accessibles

## Principes généraux

- Fournir des alternatives textuelles (sous-titres, descriptions audio).
- Assurer le contrôle complet via clavier.

## Bonnes pratiques

- Ajouter des sous-titres synchronisés (`<track>`).
- Fournir un texte alternatif pour les lecteurs d'écran.

## Accessibilité avancée

- **Sous-titres personnalisés :** Créez vos propres sous-titres synchronisés pour plus de contrôle.

### Exemple

```html
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track src="sous-titres.vtt" kind="subtitles" srclang="fr" label="Français">
</video>

<script>
  const video = document.querySelector('video');
  const track = video.textTracks[0];
  track.mode = 'showing';
</script>
```

