# Autocomplete en HTML

## Informations personnelles
- `name` : Nom complet
```html
<input type="text" autocomplete="name">
```

- `given-name` : Prénom
```html
<input type="text" autocomplete="given-name">
```

- `additional-name` : Deuxième prénom ou nom intermédiaire
```html
<input type="text" autocomplete="additional-name">
```

- `family-name` : Nom de famille
```html
<input type="text" autocomplete="family-name">
```

- `nickname` : Surnom
```html
<input type="text" autocomplete="nickname">
```

## Coordonnées

- `email` : Adresse e-mail
```html
<input type="email" autocomplete="email">
```

- `tel` : Numéro de téléphone
```html
<input type="tel" autocomplete="tel">
```

- `tel-country-code` : Indicatif téléphonique du pays
```html
<input type="text" autocomplete="tel-country-code">
```

- `tel-national` : Numéro de téléphone national
```html
<input type="tel" autocomplete="tel-national">
```

- `tel-area-code` : Indicatif régional
```html
<input type="text" autocomplete="tel-area-code">
```

- `tel-local` : Numéro de téléphone local
```html
<input type="tel" autocomplete="tel-local">
```

## Adresse

- `street-address` : Adresse postale complète
```html
<input type="text" autocomplete="street-address">
```

- `address-line1`, `address-line2`, `address-line3` : Lignes d'adresse individuelles
```html
<input type="text" autocomplete="address-line1">
<input type="text" autocomplete="address-line2">
```

- `address-level1` : État ou province
```html
<input type="text" autocomplete="address-level1">
```

- `address-level2` : Ville
```html
<input type="text" autocomplete="address-level2">
```

- `postal-code` : Code postal
```html
<input type="text" autocomplete="postal-code">
```

- `country` : Pays
```html
<input type="text" autocomplete="country">
```

## Informations de paiement

- `cc-name` : Nom sur la carte de crédit
```html
<input type="text" autocomplete="cc-name">
```

- `cc-number` : Numéro de carte de crédit
```html
<input type="text" autocomplete="cc-number">
```

- `cc-exp` : Date d'expiration de la carte
```html
<input type="text" autocomplete="cc-exp">
```

- `cc-exp-month` : Mois d'expiration de la carte
```html
<input type="text" autocomplete="cc-exp-month">
```

- `cc-exp-year` : Année d'expiration de la carte
```html
<input type="text" autocomplete="cc-exp-year">
```

- `cc-csc` : Code de sécurité de la carte
```html
<input type="text" autocomplete="cc-csc">
```

## Autres valeurs courantes

- `username` : Nom d'utilisateur
```html
<input type="text" autocomplete="username">
```

- `current-password` : Mot de passe actuel
```html
<input type="password" autocomplete="current-password">
```

- `new-password` : Nouveau mot de passe
```html
<input type="password" autocomplete="new-password">
```

- `organization` : Nom de l'entreprise ou de l'organisation
```html
<input type="text" autocomplete="organization">
```

- `language` : Langue préférée
```html
<input type="text" autocomplete="language">
```

- `bday` : Date de naissance complète
```html
<input type="date" autocomplete="bday">
```

- `bday-day`, `bday-month`, `bday-year` : Jour, mois et année de naissance séparément
```html
<input type="text" autocomplete="bday-day">
<input type="text" autocomplete="bday-month">
<input type="text" autocomplete="bday-year">
```

- `sex` : Sexe ou genre
```html
<input type="text" autocomplete="sex">
```

- `url` : URL du site web personnel
```html
<input type="url" autocomplete="url">
```

- `photo` : URL d'une photo de profil
```html
<input type="url" autocomplete="photo">
```

## Valeurs spéciales

- `off` : Désactive l'autocomplétion pour ce champ
```html
<input type="text" autocomplete="off">
```

- `on` : Active l'autocomplétion par défaut du navigateur
```html
<input type="text" autocomplete="on">
```

L'utilisation appropriée de ces valeurs `autocomplete` améliore considérablement l'expérience utilisateur en permettant aux navigateurs de remplir automatiquement les informations courantes. Cela réduit les erreurs de saisie et accélère le processus de remplissage des formulaires, ce qui est particulièrement bénéfique pour les utilisateurs de technologies d'assistance.
