## Éléments `<select>` Liste déroulante accessibles en HTML

### Principes généraux

Pour rendre un élément `<select>` accessible, il faut respecter ces principes :

- Fournir une étiquette claire et descriptive
- Assurer la navigation au clavier
- Grouper les options logiquement si nécessaire
- Offrir des instructions claires pour la sélection

### Exemple typique

```html
<label for="choix-fruit">Choisissez un fruit :</label>
<select id="choix-fruit" name="fruit">
  <option value="pomme">Pomme</option>
  <option value="banane">Banane</option>
  <option value="orange">Orange</option>
</select>
```

### Utilisation avancée

#### Groupement d'options avec `<optgroup>`

```html
<label for="choix-vehicule">Choisissez un véhicule :</label>
<select id="choix-vehicule" name="vehicule">
  <optgroup label="Voitures">
    <option value="berline">Berline</option>
    <option value="suv">SUV</option>
  </optgroup>
  <optgroup label="Motos">
    <option value="sportive">Sportive</option>
    <option value="cruiser">Cruiser</option>
  </optgroup>
</select>
```

#### Option par défaut et placeholder

```html
<select id="choix-pays" name="pays" required>
  <option value="">Sélectionnez votre pays</option>
  <option value="fr">France</option>
  <option value="be">Belgique</option>
  <option value="ch">Suisse</option>
</select>
```

#### Utilisation de `aria-describedby` pour des instructions supplémentaires

```html
<label for="choix-langue">Langue :</label>
<select id="choix-langue" name="langue" aria-describedby="langue-info">
  <option value="fr">Français</option>
  <option value="en">Anglais</option>
  <option value="es">Espagnol</option>
</select>
<p id="langue-info">Choisissez la langue dans laquelle vous souhaitez afficher le site.</p>
```

### Bonnes pratiques

- Utilisez toujours un élément `<label>` associé au `<select>`
- Évitez d'utiliser `onchange` pour soumettre automatiquement un formulaire
- Assurez-vous que le texte des options est clair et descriptif
- Limitez le nombre d'options pour éviter une liste trop longue
- Considérez l'utilisation de `<datalist>` pour des listes longues avec recherche

### Accessibilité avancée

#### Utilisation de `aria-invalid` pour indiquer une sélection invalide

```html
<select id="choix-age" name="age" aria-invalid="true" aria-describedby="age-error">
  <option value="">Sélectionnez votre tranche d'âge</option>
  <option value="18-25">18-25 ans</option>
  <option value="26-35">26-35 ans</option>
</select>
<p id="age-error" role="alert">Veuillez sélectionner une tranche d'âge.</p>
```

#### Select multiple avec instructions

```html
<label for="choix-competences">Compétences (maintenez Ctrl pour sélectionner plusieurs) :</label>
<select id="choix-competences" name="competences[]" multiple aria-describedby="competences-info">
  <option value="html">HTML</option>
  <option value="css">CSS</option>
  <option value="js">JavaScript</option>
</select>
<p id="competences-info">Vous pouvez sélectionner plusieurs compétences en maintenant la touche Ctrl enfoncée.</p>
```

Voici un exemple de code JavaScript pour permettre l'utilisation d'un élément select avec le clavier :

```javascript
const select = document.getElementById('monSelect');

select.addEventListener('keydown', (event) => {
  switch (event.key) {
    case 'ArrowUp':
    case 'ArrowLeft':
      event.preventDefault();
      if (select.selectedIndex > 0) {
        select.selectedIndex--;
      }
      break;
    case 'ArrowDown':
    case 'ArrowRight':
      event.preventDefault();
      if (select.selectedIndex < select.options.length - 1) {
        select.selectedIndex++;
      }
      break;
    case 'Enter':
    case ' ':
      event.preventDefault();
      select.click();
      break;
  }
});
```

Ce code permet de naviguer dans les options du select avec les flèches du clavier et de sélectionner une option avec la touche Entrée ou Espace.

Pour donner un exemple d'utilisation du select avec le clavier tout en restant accessible, nous pouvons ajouter des instructions visibles et cachées pour les lecteurs d'écran. Voici un exemple complet :

```html
<label for="choix-fruit">Choisissez un fruit :</label>
<select id="choix-fruit" name="fruit" aria-describedby="instructions-clavier">
  <option value="">Sélectionnez un fruit</option>
  <option value="pomme">Pomme</option>
  <option value="banane">Banane</option>
  <option value="orange">Orange</option>
</select>
<p id="instructions-clavier">
  Utilisez les flèches haut et bas pour naviguer, Entrée pour sélectionner.
  <span class="visually-hidden">
    Appuyez sur la barre d'espace pour ouvrir la liste si elle est fermée.
  </span>
</p>

<style>
  .visually-hidden {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
  }
</style>

<script>
  const select = document.getElementById('choix-fruit');

  select.addEventListener('keydown', (event) => {
    switch (event.key) {
      case 'ArrowUp':
      case 'ArrowDown':
        // La navigation par flèches est gérée nativement par le navigateur
        break;
      case 'Enter':
      case ' ':
        event.preventDefault();
        if (select.size === 1) {
          // Ouvre ou ferme la liste déroulante pour les selects simples
          const event = document.createEvent('MouseEvents');
          event.initMouseEvent('mousedown', true, true, window);
          select.dispatchEvent(event);
        }
        break;
    }
  });
</script>
```

Dans cet exemple :

1. Nous avons ajouté des instructions visibles pour tous les utilisateurs.
2. Une instruction supplémentaire est cachée visuellement mais reste accessible aux lecteurs d'écran.
3. Le JavaScript gère l'ouverture/fermeture de la liste avec la touche Espace, ce qui n'est pas toujours géré nativement par tous les navigateurs.
4. L'attribut `aria-describedby` lie les instructions au select, assurant que les lecteurs d'écran les annoncent.

Cette approche reste accessible car :

- Elle fournit des instructions claires pour tous les utilisateurs.
- Elle ne modifie pas le comportement natif du select, qui est déjà accessible au clavier.
- Elle ajoute des informations supplémentaires pour les utilisateurs de technologies d'assistance.
- Le JavaScript n'interfère pas avec la navigation standard au clavier, mais améliore l'expérience utilisateur.


Concernant le tabindex, son importance est relative :

1. Un tabindex de 0 est généralement suffisant pour les éléments select, car il les intègre dans l'ordre de tabulation naturel du document.

2. Les valeurs positives de tabindex doivent être utilisées avec précaution, car elles peuvent perturber l'ordre de navigation naturel et créer de la confusion pour les utilisateurs de technologies d'assistance.

3. Un tabindex de -1 peut être utile si vous souhaitez rendre le select focusable par programmation sans l'inclure dans l'ordre de tabulation normal.

En général, pour un élément select standard, il est préférable de ne pas utiliser de tabindex ou d'utiliser tabindex="0", laissant ainsi l'ordre de tabulation naturel du document intact.

### Checklist pour l'audit d'accessibilité des éléments Select

1. Présence d'un `<label>` correctement associé
2. Texte du label clair et descriptif
3. Groupement logique des options avec `<optgroup>` si nécessaire
4. Présence d'une option par défaut ou d'un placeholder
5. Instructions claires pour la sélection (surtout pour les selects multiples)
6. Vérification de la navigation au clavier
7. Contraste suffisant entre le texte et l'arrière-plan
8. Taille des éléments suffisante pour une utilisation facile sur mobile
9. Utilisation appropriée des attributs ARIA si nécessaire

#### Conformité RGAA

1. Vérification de la conformité avec les critères du RGAA relatifs aux formulaires
2. Respect des niveaux de conformité visés (A, AA, AAA)
3. Documentation des non-conformités éventuelles et des solutions proposées

#### Outils et méthodes

1. Test avec des lecteurs d'écran pour vérifier l'annonce correcte des options
2. Vérification de l'utilisation au clavier
3. Test sur différents appareils et navigateurs
4. Utilisation d'outils d'inspection d'accessibilité

En suivant ces recommandations, vous vous assurez que vos éléments `<select>` sont accessibles et conformes aux normes WCAG et RGAA, offrant ainsi une expérience utilisateur inclusive pour tous, y compris les personnes utilisant des technologies d'assistance.
