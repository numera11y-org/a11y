# Élément `<form>` accessible en HTML

## Exemple typique

```html
<form action="/traitement" method="post">
  <!-- Éléments du formulaire -->
</form>
```

## Attributs principaux

- `action` : URL où les données du formulaire seront envoyées
- `method` : Méthode HTTP utilisée pour l'envoi (généralement "get" ou "post")
- `name` : Nom du formulaire, utile pour le référencement par scripts
- `autocomplete` : Contrôle l'autocomplétion du navigateur ("on" ou "off")

## Bonnes pratiques d'accessibilité

1. Utilisez l'attribut `aria-labelledby` pour lier un titre au formulaire :

```html
<h2 id="form-title">Formulaire de contact</h2>
<form aria-labelledby="form-title">
  <!-- Contenu du formulaire -->
</form>
```

2. Ajoutez des instructions générales avec `aria-describedby` :

```html
<form aria-describedby="form-instructions">
  <p id="form-instructions">Les champs marqués d'un astérisque (*) sont obligatoires.</p>
  <!-- Champs du formulaire -->
</form>
```

3. Assurez-vous que tous les contrôles du formulaire sont accessibles au clavier

4. Groupez les champs reliés avec `<fieldset>` et `<legend>`

5. Utilisez des étiquettes explicites pour chaque champ avec `<label>`

## Gestion des erreurs

Utilisez l'attribut `novalidate` pour désactiver la validation native du navigateur et implémenter une validation personnalisée plus accessible :

```html
<form novalidate>
  <!-- Champs du formulaire -->
</form>
```

## Navigation au clavier

La navigation au clavier est généralement gérée automatiquement par le navigateur pour les éléments de formulaire standard. Assurez-vous que l'ordre des éléments est logique dans le code HTML.

## Exemple complet

```html
<h2 id="contact-form-title">Nous contacter</h2>
<form action="/envoyer-message" method="post" aria-labelledby="contact-form-title" aria-describedby="form-instructions" novalidate>
  <p id="form-instructions">Tous les champs sont obligatoires sauf indication contraire.</p>

  <!-- Contenu du formulaire -->

  <button type="submit">Envoyer</button>
</form>
```

Cette structure de base pour l'élément `<form>` assure une bonne accessibilité et une expérience utilisateur cohérente, tout en restant flexible pour différents types de formulaires.

## Checklist pour l'audit d'accessibilité des formulaires

1. Vérifier la présence et la pertinence de l'attribut `action`
2. S'assurer que la méthode (`method`) utilisée est appropriée pour le type de données envoyées
3. Contrôler la présence d'un titre ou d'une description claire du formulaire (via `aria-labelledby` ou `aria-describedby`)
4. Vérifier que le formulaire est entièrement utilisable au clavier
5. S'assurer que l'ordre de tabulation des éléments du formulaire est logique
6. Contrôler la présence de l'attribut `novalidate` si une validation personnalisée est implémentée
7. Vérifier que tous les contrôles du formulaire ont des étiquettes associées correctement
8. S'assurer que les messages d'erreur sont liés aux champs correspondants de manière accessible

## Conseils supplémentaires

1. Utilisez l'attribut `enctype="multipart/form-data"` pour les formulaires incluant des téléchargements de fichiers
2. Considérez l'utilisation de `autocomplete="off"` pour les champs contenant des informations sensibles
3. Implémentez une gestion d'erreur côté client pour une meilleure expérience utilisateur, tout en maintenant une validation côté serveur
4. Assurez-vous que le formulaire est responsive et s'adapte bien aux différentes tailles d'écran
5. Testez le formulaire avec différentes technologies d'assistance pour garantir une expérience cohérente pour tous les utilisateurs

## Conformité RGAA

1. Critère 11.1 : Chaque champ de formulaire a-t-il une étiquette ?
2. Critère 11.2 : Chaque étiquette associée à un champ de formulaire est-elle pertinente ?
3. Critère 11.10 : Dans chaque formulaire, le contrôle de saisie est-il utilisé de manière pertinente ?
4. Critère 11.11 : Dans chaque formulaire, le contrôle de saisie est-il accompagné, si nécessaire, de suggestions facilitant la correction des erreurs de saisie ?

## Outils et méthodes d'audit

1. Utilisez des outils d'inspection d'accessibilité comme WAVE ou aXe pour une première analyse automatique
2. Effectuez des tests manuels de navigation au clavier pour vérifier l'ordre logique et l'accessibilité de tous les éléments
3. Testez le formulaire avec différents lecteurs d'écran (NVDA, JAWS, VoiceOver) pour s'assurer que toutes les informations sont correctement annoncées
4. Vérifiez la gestion des erreurs en soumettant intentionnellement des données incorrectes
5. Testez le formulaire sur différents appareils et navigateurs pour garantir une expérience cohérente

En suivant ces recommandations et en utilisant cette checklist lors de l'audit, vous vous assurez que vos formulaires sont pleinement accessibles et conformes aux normes WCAG et RGAA.
