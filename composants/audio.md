# Élément `<audio>` en HTML accessible

## Principes généraux

Pour rendre un élément `<audio>` accessible :

- Fournir l’attribut `controls` pour permettre aux utilisateurs de lire, mettre en pause et ajuster le volume.
- Proposer une transcription textuelle pour les contenus audio afin de garantir l'accès aux utilisateurs malentendants.
- Utiliser des attributs comme `aria-describedby` ou des textes explicatifs pour offrir un contexte sur le contenu audio.
- Vérifier que les contrôles sont accessibles via le clavier et les technologies d’assistance.

## Exemple typique

```html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg" />
  Votre navigateur ne supporte pas l'élément <code>audio</code>.
</audio>
```

## Utilisation avancée

### Audio avec transcription

```html
<div>
  <audio controls>
    <source src="podcast.mp3" type="audio/mpeg" />
    Votre navigateur ne supporte pas l'élément <code>audio</code>.
  </audio>
  <p>
    <strong>Transcription :</strong> Bonjour, bienvenue dans ce podcast où nous discutons des dernières avancées en technologie...
  </p>
</div>
```

### Lecture automatique et boucle

```html
<audio autoplay loop muted>
  <source src="background-audio.mp3" type="audio/mpeg" />
  Votre navigateur ne supporte pas l'élément <code>audio</code>.
</audio>
```

### Fournir plusieurs formats pour une meilleure compatibilité

```html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg" />
  <source src="audio.ogg" type="audio/ogg" />
  Votre navigateur ne supporte pas l'élément <code>audio</code>.
</audio>
```

## Bonnes pratiques

- Ajouter l’attribut `controls` pour offrir une interface utilisateur accessible pour la lecture.
- Si le contenu audio est critique, fournir une transcription textuelle claire et complète.
- Éviter l'utilisation de la lecture automatique sans offrir un moyen de la désactiver.
- Tester l’élément `<audio>` avec divers navigateurs, lecteurs d’écran et appareils.

## Accessibilité avancée

### Ajout de descriptions

```html
<div>
  <audio controls aria-describedby="audio-description">
    <source src="audio.mp3" type="audio/mpeg" />
    Votre navigateur ne supporte pas l'élément <code>audio</code>.
  </audio>
  <p id="audio-description">Cet enregistrement présente une discussion sur les bases de l'accessibilité web.</p>
</div>
```

### Contrôle personnalisé avec ARIA

```html
<div>
  <button onclick="document.getElementById('audio').play()">Lire</button>
  <button onclick="document.getElementById('audio').pause()">Pause</button>
  <audio id="audio">
    <source src="audio.mp3" type="audio/mpeg" />
    Votre navigateur ne supporte pas l'élément <code>audio</code>.
  </audio>
</div>
```

## Navigation au clavier

- **Tab** pour naviguer entre les contrôles de l’audio.
- **Entrée** ou **Espace** pour activer/désactiver les actions (lecture, pause, volume).
- **Flèche haut/bas** pour ajuster le volume (dans certains navigateurs).
- **Flèche gauche/droite** pour avancer ou reculer dans l’audio.

Veillez à ce que tous les contrôles soient accessibles au clavier et que le focus visuel soit clairement visible.

## Checklist pour l'audit d'accessibilité

1. L’attribut `controls` est utilisé pour permettre l’interaction avec le contenu audio.
2. Une transcription textuelle est fournie pour le contenu audio critique.
3. Les contrôles du lecteur audio sont accessibles via le clavier.
4. Les descriptions appropriées (`aria-describedby`) sont ajoutées pour fournir un contexte clair si nécessaire.
5. Les audios en lecture automatique incluent l’attribut `muted` pour éviter des expériences dérangeantes.
6. L’ordre de navigation est logique et intuitif pour une interaction fluide.

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux médias temporels.
2. Respect des niveaux de conformité visés (A, AA, AAA).
3. Documentation des non-conformités éventuelles et des solutions proposées.

### Outils et méthodes

1. Tester les contrôles audio avec des lecteurs d’écran (NVDA, JAWS, VoiceOver).
2. Vérifier la navigation au clavier pour les contrôles audio.
3. Utiliser des outils comme Axe ou Wave pour analyser l’accessibilité du lecteur audio.

En suivant ces recommandations, vos éléments `<audio>` seront accessibles et conformes aux normes WCAG et RGAA, garantissant une expérience utilisateur inclusive et efficace.
