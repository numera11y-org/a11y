# Thématique 1 : Images

## 1.1 Chaque image porteuse d’information a-t-elle une alternative textuelle ?

### 1.1.1 Chaque image (balise `<img>` ou balise possédant l’attribut WAI-ARIA `role="img"`) porteuse d’information a-t-elle une alternative textuelle ?

#### Méthodologie du test 1.1.1

1. Retrouver dans le document les images structurées au moyen d’un élément `<img>` ou d’un élément possédant l’attribut WAI-ARIA `role="img"`.
2. Pour chaque image, déterminer si l’image est porteuse d’information ;
3. Dans le cas où il s’agit d’un élément `<img>`, vérifier que l’image est pourvue au moins d’une alternative textuelle parmi les suivantes ;
   - Passage de texte associé via l’attribut WAI-ARIA `aria-labelledby`
   - Contenu de l’attribut WAI-ARIA `aria-label`
   - Contenu de l’attribut `alt`
   - Contenu de l’attribut `title`
4. Dans le cas où il s’agit d’un élément possédant l’attribut WAI-ARIA `role="img"`, vérifier que l’image est pourvue au moins d’une alternative textuelle parmi les suivantes :
   *   Passage de texte associé via l’attribut WAI-ARIA `aria-labelledby`
   *   Contenu de l’attribut WAI-ARIA `aria-label`
5. Si au moins une alternative textuelle est trouvée, **le test est validé**.

### 1.1.2 Chaque zone d’une image réactive (balise `<area>`) porteuse d’information a-t-elle une alternative textuelle ?

#### Méthodologie du test 1.1.2

1. Retrouver dans le document les éléments `<area>`.
2. Pour chaque élément `<area>`, déterminer si la zone réactive est porteuse d’information.
3. Vérifier que la zone réactive est pourvue au moins d’une alternative textuelle parmi les suivantes :
   - Contenu de l’attribut WAI-ARIA `aria-label`
   - Contenu de l’attribut `alt`
4. Si au moins une alternative textuelle est trouvée, **le test est validé**.

### 1.1.3 Chaque bouton de type `image` (balise `<input>` avec l’attribut `type="image"`) a-t-il une alternative textuelle ?

#### Méthodologie du test 1.1.3

1.  Retrouver dans le document les éléments `` pourvus de l’attribut `type="image"`.
2.  Pour chaque élément `` pourvu de l’attribut type="image", déterminer si l’image utilisée est porteuse d’information.
3.  Vérifier que l’élément `` est pourvu au moins d’une alternative textuelle parmi les suivantes :
      - Passage de texte associé via l’attribut WAI-ARIA `aria-labelledby`
      - Contenu de l’attribut WAI-ARIA `aria-label`
      - Contenu de l’attribut `alt`
      - Contenu de l’attribut `title`
4.  Si au moins une alternative textuelle est trouvée, **le test est validé**.

### 1.1.4 Chaque zone cliquable d’une image réactive côté serveur est-elle doublée d’un mécanisme utilisable quel que soit le dispositif de pointage utilisé et permettant d’accéder à la même destination ?

#### Méthodologie du test 1.1.4

1.  Retrouver dans le document les éléments `` pourvus de l’attribut `ismap`.
2.  Pour chaque élément `` pourvu de l’attribut `ismap`, vérifier la présence d’un lien ou d’un ensemble de liens (ou bien d’un autre type de composant d’interface qui jouerait un rôle similaire comme une liste de sélection, par exemple) permettant d’accéder aux mêmes ressources que lorsque l’image fait l’objet d’un clic.
3.  Si c’est le cas, **le test est validé**.

### 1.1.5 Chaque image vectorielle (balise `<svg>`) porteuse d’information, vérifie-t-elle ces conditions ?

*   La balise `<svg>` possède un attribut WAI-ARIA `role="img"`.
*   La balise `<svg>` a une alternative textuelle.

#### Méthodologie du test :

1.  Retrouver dans le document les éléments `<svg>`.
2.  Pour chaque élément `<svg>`, déterminer si l’image est porteuse d’information.
3.  S’assurer que l’élément `<svg>` est pourvu d’un attribut WAI-ARIA `role="img"`. Si ce n’est pas le cas, le test est invalidé.
4.  Le cas échéant, vérifier que l’élément `<svg>` est pourvu au moins d’une alternative textuelle parmi les suivantes :
    - Contenu de l’élément `<svg>`
    - Passage de texte associé via l’attribut WAI-ARIA `aria-labelledby`
    - Contenu de l’attribut WAI-ARIA `aria-label`
5.  Si au moins une alternative textuelle est trouvée, **le test est validé**.

### 1.1.6 Chaque image objet (balise `<object>` avec l’attribut `type="image/…"`) porteuse d’information, vérifie-t-elle une de ces conditions ?

*   La balise `<object>` possède une alternative textuelle et un attribut `role="img"`.
*   L’élément `<object>` est immédiatement suivi d’un lien ou bouton adjacent permettant d’accéder à un contenu alternatif.
*   Un mécanisme permet à l’utilisateur de remplacer l’élément `<object>` par un contenu alternatif.

#### Méthodologie du test 1.1.6
 
1. Retrouver dans le document les balises ouvrantes `` pourvues de l’attribut `type=“image/…”`.
2.  Pour chaque balise ouvrante `` pourvue de l’attribut `type=“image/…”`, déterminer si l’image utilisée est porteuse d’information.
3.  Vérifier que l’élément `` est pourvu d’un attribut WAI-ARIA `role=“img”`.
4.  Vérifier que l’élément `` est pourvu au moins d’une alternative textuelle parmi les suivantes :
    - Passage de texte associé via l’attribut WAI-ARIA `aria-labelledby`
    - Contenu de l’attribut WAI-ARIA `aria-label`
    - Contenu de l’attribut `title`
5.  Si au moins une alternative textuelle est trouvée, **le test est validé**.
6.  Sinon, vérifier que l’élément `<object>` est :
    - Soit immédiatement suivi d’un lien ou bouton adjacent permettant d’accéder à un contenu alternatif.
    - Soit un mécanisme permet à l’utilisateur de remplacer l’élément `` par un contenu alternatif.
7.  Si c’est le cas, **le test est validé**.

### 1.1.7 Chaque image embarquée (balise `` avec l’attribut `type="image/…"`) porteuse d’information, vérifie-t-elle une de ces conditions ?

*   La balise `` possède une alternative textuelle et un attribut `role="img"`.
*   L’élément `` est immédiatement suivi d’un lien ou bouton adjacent permettant d’accéder à un contenu alternatif.
*   Un mécanisme permet à l’utilisateur de remplacer l’élément `` par un contenu alternatif.

#### Méthodologie du test 1.1.7 

1.  Pour chaque élément `<embed>` pourvu de l’attribut `type="image/…"`, déterminer si l’image utilisée est porteuse d’information.
2.  Vérifier que l’élément `<embed>` est pourvu d’un attribut WAI-ARIA `role="img"`.
3.  Vérifier que l’élément `<embed>` est pourvu au moins d’une alternative textuelle parmi les suivantes :
    - Passage de texte associé via l’attribut WAI-ARIA `aria-labelledby`
    - Contenu de l’attribut WAI-ARIA `aria-label`
    - Contenu de l’attribut `title`
4.  Si au moins une alternative textuelle est trouvée, **le test est validé**.
5.  Sinon, vérifier que l’élément `<embed>` est :
    - Soit immédiatement suivi d’un lien ou bouton adjacent permettant d’accéder à un contenu alternatif.
    - Soit un mécanisme permet à l’utilisateur de remplacer l’élément `<embed>` par un contenu alternatif.
6.  Si c’est le cas, **le test est validé**.

### 1.1.8 Chaque image bitmap (balise `<canvas>`) porteuse d’information, vérifie-t-elle une de ces conditions ?

*   La balise `<canvas>` possède une alternative textuelle et un attribut `role="img"`.
*   Un contenu alternatif est présent entre les balises `<canvas>` et `</canvas>`.
*   L’élément `<canvas>` est immédiatement suivi d’un lien ou bouton adjacent permettant d’accéder à un contenu alternatif.
*   Un mécanisme permet à l’utilisateur de remplacer l’élément `<canvas>` par un contenu alternatif.

#### Méthodologie du test 1.1.8

1.  Retrouver dans le document les éléments `<canvas>`.
2.  Pour chaque élément `<canvas>`, déterminer si l’image utilisée est porteuse d’information.
3.  Vérifier que l’élément `<canvas>` est pourvu d’un attribut WAI-ARIA `role=“img”`.
4.  Vérifier que la balise ouvrante `<canvas>` est pourvue au moins d’une alternative textuelle parmi les suivantes :
    - Passage de texte associé via l’attribut WAI-ARIA `aria-labelledby`
    - Contenu de l’attribut WAI-ARIA `aria-label`
5.  Si au moins une alternative textuelle est trouvée, **le test est validé**.
6.  Si les étapes 3 et 4 ne sont pas satisfaites, vérifier que l’élément `<canvas>` est :
    - Soit pourvu d’un contenu alternatif présent entre les balises `<canvas>` et `</canvas>`.
    - Soit immédiatement suivi d’un lien ou bouton adjacent permettant d’accéder à un contenu alternatif.
    - Soit un mécanisme permet à l’utilisateur de remplacer l’élément `<canvas>` par un contenu alternatif.
7.  Si c’est le cas, **le test est validé**.

> **Note** : si l’élément `<canvas>` dispose d’un rôle `img`, son alternative ne peut être fournie que par les techniques listées à l’étape 4.

## 1.2 Chaque image de décoration est-elle correctement ignorée par les technologies d’assistance ?

### 1.2.1 Chaque image (balise `<img>`) de décoration, sans légende, vérifie-t-elle une de ces conditions ?

*   La balise `` possède un attribut `alt` vide (`alt=""`) et est dépourvue de tout autre attribut permettant de fournir une alternative textuelle.
*   La balise `` possède un attribut WAI-ARIA `aria-hidden="true"` ou `role="presentation"`.

#### Méthodologie du test 1.2.1
 
1. Retrouver dans le document les images décoratives dépourvues de légende structurées au moyen d’un élément `<img>`.
2.  Pour chaque image, vérifier que l’image ne possède pas d’attributs `aria-labelledby`, `aria-label` ou `title` et qu’elle possède :
    - Soit un attribut `alt` vide (`alt=""`).
    - Soit un attribut WAI-ARIA `aria-hidden="true"` ou `role="presentation"`.
3.  Si c’est le cas pour chaque image, **le test est validé**.

### 1.2.2 Chaque zone non cliquable (balise `<area>` sans attribut `href`) de décoration, vérifie-t-elle une de ces conditions ?

*   La balise `` possède un attribut `alt` vide (`alt=""`) et est dépourvue de tout autre attribut permettant de fournir une alternative textuelle.
*   La balise `` possède un attribut WAI-ARIA `aria-hidden="true"` ou `role="presentation"`.

#### Méthodologie du test 1.2.2

1.  Retrouver dans le document les images décoratives structurées au moyen d’un élément `` (sans attribut `href`).
2.  Pour chaque image, vérifier que l’élément `` ne possède pas d’attributs `aria-labelledby`, `aria-label` ou `title` et qu’il possède :
    - Soit un attribut `alt` vide (`alt=""`).
    - Soit un attribut WAI-ARIA `aria-hidden="true"` ou `role="presentation"`.
3.  Si c’est le cas pour chaque image, **le test est validé**.

### 1.2.3 Chaque image objet (balise `<object>` avec l’attribut `type="image/…"`) de décoration, sans légende, vérifie-t-elle ces conditions ?

*   La balise `<object>` possède un attribut WAI-ARIA `aria-hidden="true"`.
*   La balise `<object>` est dépourvue d’alternative textuelle.
*   Il n’y a aucun texte faisant office d’alternative textuelle entre `` et ``.

#### Méthodologie du test 1.2.3

1.  Retrouver dans le document les images décoratives structurées dépourvues de légende au moyen d’un élément `<object>` (avec un attribut `type="image/…"`).
2.  Pour chaque image, vérifier que la balise ouvrante `` ne possède pas d’attributs `aria-labelledby`, `aria-label` ou `title` et qu’elle :
    - Possède un attribut WAI-ARIA `aria-hidden="true"`.
    - Et est dépourvue d’alternative textuelle.
    - Et est dépourvue d’un contenu alternatif présent entre les balises `<object>` et `</object>`.
3.  Si c’est le cas pour chaque image, **le test est validé**.
