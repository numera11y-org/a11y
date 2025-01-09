## Tableaux accessibles

### Principes généraux

- Assurer une structure logique avec `<thead>`, `<tbody>` et `<caption>`.
- Fournir des en-têtes descriptifs avec `<th>`.

### Bonnes pratiques

- Ajouter une légende via `<caption>`.
- Utiliser `scope="col"` ou `scope="row"` pour associer les en-têtes aux cellules.

### Accessibilité avancée

- **Descriptions complexes :** Utilisez `aria-describedby` pour fournir des détails supplémentaires sur le contenu du tableau.

#### Exemple

```html
<table>
  <caption>Statistiques des ventes</caption>
  <thead>
    <tr>
      <th scope="col">Produit</th>
      <th scope="col">Ventes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Produit A</td>
      <td>100</td>
    </tr>
  </tbody>
</table>
```

