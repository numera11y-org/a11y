# Rôles de structure de document

## role="banner"

**Utilisation** : Pour identifier l'en-tête principal d'une page, généralement contenant le logo et la navigation principale.

**Quand l'utiliser** : Sur l'élément `<header>` principal de la page. Ne pas utiliser sur des en-têtes de sections.

## role="main"

**Utilisation** : Identifie le contenu principal de la page.

**Quand l'utiliser** : Sur l'élément `<main>` ou sur le conteneur principal du contenu. Une seule utilisation par page.

## role="navigation"

**Utilisation** : Pour les sections contenant des liens de navigation.

**Quand l'utiliser** : Sur les éléments `<nav>` ou les conteneurs de menus de navigation.

## role="complementary"

**Utilisation** : Pour du contenu qui complète le contenu principal mais reste significatif seul.

**Quand l'utiliser** : Typiquement sur les `<aside>` ou les barres latérales.

## role="contentinfo"

**Utilisation** : Pour les informations sur le document (droits d'auteur, liens connexes).

**Quand l'utiliser** : Généralement sur le `<footer>` principal de la page.

---

# Rôles de structure de contenu

## role="article"

**Utilisation** : Pour un contenu autonome et indépendant.

**Quand l'utiliser** : Sur les éléments `<article>` ou pour des sections de contenu pouvant être distribuées indépendamment.

## role="section"

**Utilisation** : Pour grouper du contenu thématique.

**Quand l'utiliser** : Sur les éléments `<section>` ou pour diviser le contenu en parties distinctes.

## role="list" et role="listitem"

**Utilisation** : Pour identifier une liste et ses éléments.

**Quand l'utiliser** : Uniquement si vous ne pouvez pas utiliser les balises `<ul>`, `<ol>` et `<li>` natives.

---

# Rôles interactifs

## role="button"

**Utilisation** : Pour les éléments cliquables qui déclenchent une action.

**Quand l'utiliser** : Sur des éléments non-boutons (comme `<div>` ou `<span>`) stylisés en boutons. Préférer la balise `<button>` native quand possible.

## role="link"

**Utilisation** : Pour les éléments cliquables qui mènent à une autre page ou ressource.

**Quand l'utiliser** : Sur des éléments non-liens stylisés en liens. Préférer la balise `<a>` native quand possible.

## role="checkbox" et role="radio"

**Utilisation** : Pour les éléments de formulaire à cocher ou les boutons radio.

**Quand l'utiliser** : Sur des éléments personnalisés remplaçant les `<input type="checkbox">` ou `<input type="radio">` natifs.

## role="tablist", role="tab", et role="tabpanel"

**Utilisation** : Pour créer une interface à onglets.

**Quand l'utiliser** : Sur les conteneurs d'onglets, les onglets individuels et les panneaux de contenu associés.

---

# Rôles de structure de données

## role="table", role="row", role="cell"

**Utilisation** : Pour structurer des données tabulaires.

**Quand l'utiliser** : Uniquement si vous ne pouvez pas utiliser les balises `<table>`, `<tr>`, `<td>` natives.

## role="grid"

**Utilisation** : Pour des grilles de données interactives.

**Quand l'utiliser** : Sur des tableaux complexes avec fonctionnalités interactives (tri, filtrage, etc.).

---

# Conseils généraux d'utilisation

- Utilisez toujours les éléments HTML sémantiques natifs quand ils sont disponibles.
- N'utilisez les rôles ARIA que lorsque la sémantique HTML native ne suffit pas.
- Assurez-vous que l'utilisation des rôles est cohérente avec le comportement et l'apparence de l'élément.
- Testez toujours l'accessibilité avec des lecteurs d'écran pour vérifier l'efficacité de vos rôles ARIA.
