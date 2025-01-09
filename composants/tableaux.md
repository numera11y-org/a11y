## Élément `<table>` en HTML accessible

### Principes généraux

Pour rendre un élément `<table>` accessible, il faut respecter ces principes :

- Utiliser une structure sémantique appropriée avec les balises `<table>`, `<tr>`, `<th>` et `<td>`
- Associer correctement les cellules d'en-tête et de données
- Fournir un titre et un résumé au tableau si nécessaire
- S'assurer que le contenu est compréhensible lorsqu'il est linéarisé
- Éviter d'utiliser les tableaux pour la mise en page

### Exemple typique

```html
<table>
  <caption>Titre du tableau</caption>
  <thead>
    <tr>
      <th scope="col">En-tête 1</th>
      <th scope="col">En-tête 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Donnée 1</td>
      <td>Donnée 2</td>
    </tr>
  </tbody>
</table>
```

### Utilisation avancée

#### Tableau complexe avec en-têtes multiples

```html
<table>
  <caption>Ventes trimestrielles par région</caption>
  <thead>
    <tr>
      <th rowspan="2" scope="col">Région</th>
      <th colspan="4" scope="colgroup">Trimestres</th>
    </tr>
    <tr>
      <th scope="col">T1</th>
      <th scope="col">T2</th>
      <th scope="col">T3</th>
      <th scope="col">T4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Nord</th>
      <td>100€</td>
      <td>120€</td>
      <td>90€</td>
      <td>110€</td>
    </tr>
  </tbody>
</table>
```

### Bonnes pratiques

- Utiliser `<caption>` pour donner un titre au tableau
- Utiliser `<th>` pour les cellules d'en-tête avec l'attribut `scope` approprié
- Structurer le tableau avec `<thead>`, `<tbody>` et `<tfoot>` si nécessaire
- Éviter les tableaux imbriqués ou les tableaux pour la mise en page
- S'assurer que le contenu est compréhensible lorsqu'il est lu de manière linéaire

### Accessibilité avancée

#### Utilisation des attributs `id` et `headers` pour les tableaux complexes

```html
<table>
  <caption>Horaires des cours</caption>
  <thead>
    <tr>
      <th id="heure">Heure</th>
      <th id="lundi">Lundi</th>
      <th id="mardi">Mardi</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th id="h9" headers="heure">9h00</th>
      <td headers="lundi h9">Mathématiques</td>
      <td headers="mardi h9">Français</td>
    </tr>
  </tbody>
</table>
```

### Navigation au clavier

Les tableaux HTML sont naturellement navigables au clavier. Les utilisateurs peuvent utiliser les touches fléchées pour se déplacer entre les cellules. Cependant, il est important de s'assurer que l'ordre de lecture est logique et que les relations entre les cellules sont claires pour les technologies d'assistance.

### Résumé du tableau

Pour les tableaux complexes, il est recommandé de fournir un résumé. Bien que l'attribut `summary` soit déprécié en HTML5, on peut inclure un résumé dans la balise `<caption>` ou utiliser un élément adjacent au tableau avec un `id` référencé par `aria-describedby` sur la balise `<table>`.

```html
<p id="resume-tableau">Ce tableau présente les ventes trimestrielles par région.</p>
<table aria-describedby="resume-tableau">
  <!-- Contenu du tableau -->
</table>
```

### Checklist pour l'audit d'accessibilité

1. Vérifier que le tableau utilise une structure sémantique correcte (`<table>`, `<tr>`, `<th>`, `<td>`)
2. S'assurer que chaque tableau a un titre (`<caption>`)
3. Vérifier que les cellules d'en-tête utilisent `<th>` avec l'attribut `scope` approprié
4. Pour les tableaux complexes, vérifier l'utilisation correcte des attributs `id` et `headers`
5. S'assurer que le contenu du tableau est compréhensible lorsqu'il est lu de manière linéaire
6. Vérifier que les tableaux de mise en page sont évités ou utilisent `role="presentation"`
7. Tester la navigation au clavier dans le tableau
8. Vérifier la présence d'un résumé pour les tableaux complexes

#### Conformité RGAA

1. Critère 5.1 : Chaque tableau de données complexe a-t-il un résumé ?
2. Critère 5.2 : Pour chaque tableau de données complexe ayant un résumé, celui-ci est-il pertinent ?
3. Critère 5.3 : Pour chaque tableau de mise en page, le contenu linéarisé reste-t-il compréhensible ?
4. Critère 5.4 : Chaque tableau de données a-t-il un titre ?
5. Critère 5.5 : Pour chaque tableau de données ayant un titre, celui-ci est-il pertinent ?
6. Critère 5.6 : Pour chaque tableau de données, chaque en-tête de colonnes et chaque en-tête de lignes sont-ils correctement déclarés ?
7. Critère 5.7 : Pour chaque tableau de données, la technique appropriée permettant d'associer chaque cellule avec ses en-têtes est-elle utilisée ?
8. Critère 5.8 : Chaque tableau de mise en page ne doit pas utiliser d'éléments propres aux tableaux de données. Cette règle est-elle respectée ?

#### Outils et méthodes

1. Utiliser des outils d'inspection du code comme les DevTools des navigateurs
2. Tester avec des lecteurs d'écran pour vérifier la compréhension du tableau
3. Utiliser des outils automatisés comme WAVE ou AChecker pour détecter les problèmes d'accessibilité courants
4. Effectuer des tests manuels de navigation au clavier
5. Vérifier le contraste des couleurs utilisées dans le tableau
