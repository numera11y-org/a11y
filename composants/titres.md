# Titres HTML (H1 à H6) accessibles

## Principes généraux

Pour rendre les titres HTML accessibles, il faut respecter ces principes :

- Utiliser une structure hiérarchique logique
- Assurer la cohérence entre le contenu et le niveau de titre
- Éviter de sauter des niveaux de titre
- Utiliser des titres descriptifs et concis

## Exemple typique

```html
<h1>Titre principal</h1>
<h2>Sous-titre</h2>
<h3>Sous-sous-titre</h3>
<h4>Titre de niveau 4</h4>
<h5>Titre de niveau 5</h5>
<h6>Titre de niveau 6</h6>
```

## Utilisation correcte des niveaux de titre

### H1 : Titre principal de la page

```html
<h1>Bienvenue sur notre site de recettes de cuisine</h1>
```

### H2 : Sections principales

```html
<h2>Recettes populaires</h2>
<h2>Catégories de plats</h2>
```

### H3 : Sous-sections

```html
<h3>Entrées</h3>
<h3>Plats principaux</h3>
```

### H4-H6 : Niveaux de titre supplémentaires

```html
<h4>Recettes végétariennes</h4>
<h5>Ingrédients</h5>
<h6>Étapes de préparation</h6>
```

## Bonnes pratiques

- Utilisez un seul `<h1>` par page, généralement pour le titre principal
- Maintenez une hiérarchie logique sans sauter de niveaux (ex: ne pas passer de `<h2>` à `<h4>`)
- Assurez-vous que le texte des titres soit descriptif et concis
- Évitez d'utiliser les balises de titre uniquement pour le style visuel

## Accessibilité avancée

### Utilisation de aria-label pour des titres invisibles

```html
<h2 aria-label="Section de navigation">
  <span class="icon-nav"></span>
</h2>
```

### Titres avec des liens

```html
<h3><a href="#section-1">Section 1: Introduction</a></h3>
```

## Checklist pour l'audit d'accessibilité des titres

Lors d'un audit d'accessibilité, vérifiez les points suivants pour chaque titre :

1. Présence d'un `<h1>` unique sur la page
2. Hiérarchie logique et cohérente des titres (H1 > H2 > H3, etc.)
3. Absence de niveaux de titre sautés
4. Pertinence et concision du contenu des titres
5. Cohérence entre le contenu visuel et la structure des titres
6. Utilisation appropriée des titres (pas uniquement pour le style)
7. Vérification de l'accessibilité avec des lecteurs d'écran

### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs à la structure de l'information
2. Respect des niveaux de conformité visés (A, AA, AAA)
3. Documentation des non-conformités éventuelles et des solutions proposées

### Outils et méthodes

1. Utilisation d'outils d'inspection de la structure des titres (ex: extensions de navigateur)
2. Inspection manuelle du code source
3. Tests avec des technologies d'assistance pour vérifier la navigation par titres
4. Vérification de la cohérence visuelle et sémantique des titres

En suivant ces recommandations, vous vous assurez que la structure des titres de votre site web est accessible et conforme aux normes WCAG et RGAA, facilitant ainsi la navigation et la compréhension du contenu pour tous les utilisateurs, y compris ceux utilisant des technologies d'assistance.
