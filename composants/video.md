# Élément `<video>` en HTML accessible

## Principes généraux

Pour rendre un élément `<video>` accessible :

- Fournir des sous-titres synchronisés pour rendre le contenu compréhensible aux utilisateurs malentendants.
- Proposer une transcription textuelle ou une audiodescription pour le contenu visuel significatif.
- Ajouter un attribut `controls` pour permettre aux utilisateurs d’interagir avec le lecteur (lecture, pause, volume, etc.).
- Inclure des alternatives textuelles pertinentes pour les vidéos décoratives ou informatives.
- S'assurer que le lecteur vidéo est utilisable au clavier et avec les technologies d’assistance.

## Exemple typique

```html
<video controls>
  <source src="video.mp4" type="video/mp4" />
  Votre navigateur ne supporte pas l'élément <code>video</code>.
</video>
```

## Utilisation avancée

### Vidéo avec sous-titres

```html
<video controls>
  <source src="video.mp4" type="video/mp4" />
  <track src="sous-titres.vtt" kind="subtitles" srclang="fr" label="Français" />
  <track src="subtitles-en.vtt" kind="subtitles" srclang="en" label="English" />
  Votre navigateur ne supporte pas l'élément <code>video</code>.
</video>
```

### Vidéo avec transcription et audiodescription

```html
<div>
  <video controls>
    <source src="video.mp4" type="video/mp4" />
    <track src="audiodescription.vtt" kind="descriptions" srclang="fr" label="Audiodescription" />
    Votre navigateur ne supporte pas l'élément <code>video</code>.
  </video>
  <p>
    <strong>Transcription :</strong> Voici une transcription textuelle complète de la vidéo.
  </p>
</div>
```

### Vidéo en boucle avec lecture automatique

```html
<video autoplay loop muted>
  <source src="background-video.mp4" type="video/mp4" />
  Votre navigateur ne supporte pas l'élément <code>video</code>.
</video>
```

## Bonnes pratiques

- Inclure l’attribut `controls` pour que les utilisateurs puissent interagir avec la vidéo.
- Ajouter des sous-titres via `<track kind="subtitles">` pour rendre le contenu accessible aux malentendants ou aux utilisateurs parlant une autre langue.
- Utiliser l’attribut `muted` pour désactiver le son par défaut lorsque la vidéo est configurée en lecture automatique.
- Fournir une alternative textuelle pour les vidéos critiques (par exemple, via une transcription).
- Tester la compatibilité et les fonctionnalités dans différents navigateurs et sur divers appareils.

## Accessibilité avancée

### Gestion des sous-titres multiples

```html
<video controls>
  <source src="video.mp4" type="video/mp4" />
  <track src="sous-titres-fr.vtt" kind="subtitles" srclang="fr" label="Français" default />
  <track src="subtitles-en.vtt" kind="subtitles" srclang="en" label="English" />
  Votre navigateur ne supporte pas l'élément <code>video</code>.
</video>
```

### Personnalisation des sous-titres via CSS

```html
<style>
  ::cue {
    color: white;
    background: rgba(0, 0, 0, 0.7);
    font-size: 16px;
    padding: 5px;
    border-radius: 3px;
  }
</style>
<video controls>
  <source src="video.mp4" type="video/mp4" />
  <track src="sous-titres.vtt" kind="subtitles" srclang="fr" label="Français" />
</video>
```

## Navigation au clavier

- **Tab** pour naviguer dans les contrôles du lecteur vidéo.
- **Entrée** ou **Espace** pour activer ou désactiver les options (lecture, pause, volume, etc.).
- **Flèche gauche/droite** pour reculer ou avancer dans la vidéo.
- **Flèche haut/bas** pour augmenter ou diminuer le volume.

Assurez-vous que tous les contrôles sont accessibles via le clavier et que le focus visuel est clairement visible.

## Checklist pour l'audit d'accessibilité

1. L’élément `<video>` inclut des sous-titres synchronisés pour le contenu audio.
2. Une transcription textuelle est fournie pour les vidéos informatives ou critiques.
3. Les contrôles de lecture sont disponibles et utilisables au clavier.
4. Les vidéos en lecture automatique sont silencieuses par défaut (via `muted`).
5. Les sous-titres et audiodescriptions sont correctement configurés avec des éléments `<track>`.
6. Le lecteur vidéo est compatible avec les lecteurs d’écran et annoncé correctement.
7. Les couleurs et contrastes des sous-titres respectent les critères WCAG.

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux médias temporels.
2. Respect des niveaux de conformité visés (A, AA, AAA).
3. Documentation des non-conformités éventuelles et des solutions proposées.

### Outils et méthodes

1. Tester les sous-titres et contrôles avec des lecteurs d’écran (NVDA, JAWS, VoiceOver).
2. Vérifier la navigation au clavier sur les contrôles vidéo.
3. Utiliser des outils comme Axe pour analyser l’accessibilité du lecteur vidéo.

En suivant ces recommandations, vos vidéos seront accessibles, garantissant une expérience utilisateur inclusive et conforme aux normes WCAG et RGAA.
