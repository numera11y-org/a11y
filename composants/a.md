## Élément `<a>` (lien) accessible en HTML

### Principes généraux

Pour rendre un lien accessible, il faut respecter ces principes :

- Fournir un texte de lien clair et descriptif
- Assurer la navigation au clavier
- Distinguer visuellement les liens du texte environnant
- Indiquer les liens qui s'ouvrent dans une nouvelle fenêtre ou mènent à un téléchargement

### Exemple typique

```html
<a href="https://example.com">Visitez notre site web</a>
```

### Utilisation avancée

#### Lien avec titre explicatif

```html
<a href="https://example.com/rapport-2023.pdf" title="Télécharger le rapport annuel 2023 (PDF, 2.5 Mo)">
  Rapport annuel 2023
</a>
```

#### Lien s'ouvrant dans une nouvelle fenêtre

```html
<a href="https://example.com" target="_blank" rel="noopener noreferrer">
  Visitez notre site partenaire
  <span class="visually-hidden">(s'ouvre dans une nouvelle fenêtre)</span>
</a>
```

#### Lien de téléchargement

```html
<a href="/documents/brochure.pdf" download>
  Télécharger notre brochure
  <span class="visually-hidden">(PDF, 1.2 Mo)</span>
</a>
```

### Bonnes pratiques

- Utilisez des textes de lien descriptifs et évitez les "cliquez ici" ou "en savoir plus"
- Assurez-vous que les liens sont visuellement distincts du texte environnant (couleur, soulignement)
- Maintenez la cohérence dans le style des liens à travers le site
- Évitez d'ouvrir de nouvelles fenêtres sans prévenir l'utilisateur

### Accessibilité avancée

#### Utilisation d'aria-label pour des liens plus descriptifs

```html
<a href="https://example.com/produit123" aria-label="En savoir plus sur le produit XYZ">
  En savoir plus
</a>
```

#### Indication des liens externes avec une icône

```html
<a href="https://site-externe.com" class="external-link">
  Site partenaire
  <svg aria-hidden="true" class="external-icon" viewBox="0 0 24 24">
    <!-- Icône SVG indiquant un lien externe -->
  </svg>
</a>

<style>
  .external-link {
    display: inline-flex;
    align-items: center;
  }
  .external-icon {
    width: 1em;
    height: 1em;
    margin-left: 0.25em;
  }
</style>
```

### Navigation au clavier

Les liens sont nativement accessibles au clavier :

- Les utilisateurs peuvent naviguer entre les liens en utilisant la touche Tab
- L'activation du lien se fait avec la touche Entrée lorsqu'il a le focus
- L'état de focus doit être clairement visible (outline par défaut du navigateur ou style personnalisé)

```css
a:focus {
  outline: 2px solid #4A90E2;
  outline-offset: 2px;
}
```
### Ancre

Une ancre est un lien vers un endroit précis d'une page web, qu'il s'agisse de la page courante ou d'une autre page. Elle permet de positionner le navigateur à un endroit spécifique du document.

Pour créer une ancre, on utilise l'attribut `id` sur l'élément cible :

```html
<h2 id="section1">Section 1</h2>
```

Pour créer un lien vers cette ancre, on utilise une balise `<a>` avec l'attribut `href` contenant le caractère `#` suivi de l'identifiant de l'ancre :

```html
<a href="#section1">Aller à la Section 1</a>
```

Les ancres sont particulièrement utiles pour :
- Créer des liens d'évitement, améliorant ainsi l'accessibilité du site
- Permettre une navigation rapide dans de longues pages
- Créer des liens de retour en haut de page

Il est important de noter que les ancres jouent un rôle dans l'accessibilité en facilitant la navigation pour les utilisateurs de technologies d'assistance.

### Ancre et accessibilité

Bien que les ancres HTML ne nécessitent pas d'instructions ARIA spécifiques pour fonctionner, il existe des bonnes pratiques pour améliorer leur accessibilité :

1. Utilisez des textes de lien descriptifs pour les ancres, évitant les "cliquez ici" ou "#".

2. Si le texte visible du lien n'est pas suffisamment descriptif, vous pouvez utiliser `aria-label` pour fournir un texte plus explicite aux technologies d'assistance :

```html
<a href="#section1" aria-label="Aller à la section Introduction">Intro</a>
```

3. Pour les ancres qui servent de liens d'évitement, vous pouvez utiliser `role="navigation"` sur le conteneur :

```html
<nav role="navigation">
  <a href="#contenu">Aller au contenu principal</a>
</nav>
```

4. Si l'ancre fait partie d'une table des matières, vous pouvez utiliser `role="doc-toc"` sur le conteneur.

5. Pour les liens de retour en haut de page, assurez-vous qu'ils sont clairement identifiables :

```html
<a href="#top" aria-label="Retour en haut de la page">↑ Haut</a>
```

Ces pratiques améliorent l'expérience des utilisateurs de technologies d'assistance sans nécessiter d'instructions ARIA spécifiques aux ancres.

### Checklist pour l'audit d'accessibilité des liens

1. Texte des liens clair et descriptif
2. Liens visuellement distincts du texte environnant
3. État de focus visible et suffisamment contrasté
4. Indication claire pour les liens s'ouvrant dans une nouvelle fenêtre
5. Information sur le type et la taille des fichiers pour les liens de téléchargement
6. Cohérence des styles de liens à travers le site
7. Vérification de l'accessibilité au clavier (navigation et activation)
8. Test avec des lecteurs d'écran pour s'assurer que le contexte est bien compris

#### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux liens (thématique 6)
2. Respect des niveaux de conformité visés (A, AA, AAA)
3. Documentation des non-conformités éventuelles et des solutions proposées

#### Outils et méthodes

1. Inspection visuelle des liens dans différents états (normal, survol, focus, visité)
2. Test manuel de navigation au clavier
3. Utilisation d'outils d'inspection d'accessibilité (ex: WAVE, aXe)
4. Vérification du contraste des liens avec des outils dédiés
5. Tests avec différentes technologies d'assistance

En suivant ces recommandations, vous vous assurez que vos liens sont accessibles et conformes aux normes WCAG et RGAA, offrant ainsi une expérience de navigation inclusive pour tous les utilisateurs.
