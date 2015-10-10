title: Assistants
---
Les assistants sont utilisés dans les modèles et vous permettent d'insérer rapidement des snippets.

## URL

### url_for

Retourne une URL avec le chemin racine préfixé. Vous devriez utiliser cet assistant plutôt que `config.root + path` depuis Hexo 2.7.

``` js
<%- url_for(path) %>
```

### relative_url

Retourne l'URL relative de `from` vers `to`.

``` js
<%- relative_url(from, to) %>
```

### gravatar

Insère une image Gravatar.

``` js
<%- gravatar(email, [size]);
```

**Exemples :**

``` js
<%- gravatar('a@abc.com') %>
// http://www.gravatar.com/avatar/b9b00e66c6b8a70f88c73cb6bdb06787

<%- gravatar('a@abc.com', 40) %>
// http://www.gravatar.com/avatar/b9b00e66c6b8a70f88c73cb6bdb06787?s=40
```

## Balises HTML

### css

Charge des fichiers CSS. `path` peut être un tableau ou une chaîne de caractères. Si `path` n'est pas préfixé par `/` ou n'importe quel protocole, il sera préfixé par l'URL racine. Si vous n'ajoutez pas l'extension `.css` après `path`, elle sera automatiquement ajoutée.

``` js
<%- css(path, ...) %>
```

**Exemples :**

``` js
<%- css('style.css') %>
// <link rel="stylesheet" href="/style.css" type="text/css">

<%- css(['style.css', 'screen.css']) %>
// <link rel="stylesheet" href="/style.css" type="text/css">
// <link rel="stylesheet" href="/screen.css" type="text/css">
```

### js

Charge des fichiers JavaScript. `path` peut être un tableau ou une chaîne de caractères. Si `path` n'est pas préfixé par `/` ou n'importe quel protocole, il sera préfixé par l'URL racine. Si vous n'ajoutez pas l'extension `.js` après `path`, elle sera automatiquement ajoutée.

``` js
<%- js(path, ...) %>
```

**Examples:**

``` js
<%- js('script.js') %>
// <script type="text/javascript" src="/script.js"></script>

<%- js(['script.js', 'gallery.js']) %>
// <script type="text/javascript" src="/script.js"></script>
// <script type="text/javascript" src="/gallery.js"></script>
```

### link_to

Insère un lien.

``` js
<%- link_to(path, [text], [options]) %>
```

Option | Description | Par défaut
--- | --- | ---
`external` | Ouvre le lien dans un nouvel onglet | false
`class` | Nom de classe |
`id` | ID |

**Examples:**

``` js
<%- link_to('http://www.google.com') %>
// <a href="http://www.google.com" title="http://www.google.com">http://www.google.com</a>

<%- link_to('http://www.google.com', 'Google') %>
// <a href="http://www.google.com" title="Google">Google</a>

<%- link_to('http://www.google.com', 'Google', {external: true}) %>
// <a href="http://www.google.com" title="Google" target="_blank" rel="external">Google</a>
```

### mail_to

Insère un lien de type `mailto` (pour envoyer un courriel).

``` js
<%- mail_to(path, [text], [options]) %>
```

Option | Description
--- | ---
`class` | Nom de classe
`id` | ID
`subject` | Sujet du courriel
`cc` | Copie carbone (Cc)
`bcc` | Copie carbone invisible (Cci)
`body` | Contenus du courriel

**Exemples :**

``` js
<%- mail_to('a@abc.com') %>
// <a href="mailto:a@abc.com" title="a@abc.com">a@abc.com</a>

<%- mail_to('a@abc.com', 'Email') %>
// <a href="mailto:a@abc.com" title="Email">Email</a>
```

### image_tag

Insère une image.

``` js
<%- image_tag(path, [options]) %>
```

Option | Description
--- | ---
`alt` | Texte alternatif de l'image
`class` | Nom de classe
`id` | ID
`width` | Largeur de l'image
`height` | Hauteur de l'image

### favicon_tag

Insère une favicon.

``` js
<%- favicon_tag(path) %>
```

### feed_tag

Insère un lien de flux.

``` js
<%- feed_tag(path, [options]) %>
```

Option | Description | Par défaut
--- | --- | ---
`title` | Titre du flux |
`type` | Type de flux | atom

### Balises conditionnelles

### is_current

Vérifie si `path` correspond à l'URL de la page actuelle. Utilisez l'option `strict` pour activer la correspondance stricte.

``` js
<%- is_current(path, [strict]) %>
```

### is_home

Vérifie si la page actuelle est la page d'accueil.

``` js
<%- is_home() %>
```

### is_post

Vérifie si la page actuelle est un post.

``` js
<%- is_post() %>
```

### is_archive

Vérifie si la page actuelle est une page d'archive.

``` js
<%- is_archive() %>
```

### is_year

Vérifie si la page actuelle est une page d'archive annuelle.

``` js
<%- is_year() %>
```

### is_month

Vérifie si la page actuelle est une page d'archive mensuelle.

``` js
<%- is_month() %>
```

### is_category

Vérifie si la page actuelle est une page de catégorie.

``` js
<%- is_category() %>
```

### is_tag

Vérifie si la page actuelle est une page d'étiquette.

``` js
<%- is_tag() %>
```

## Manipulation des chaînes

### trim

Supprime les espaces de début et de fin d'une chaîne.

``` js
<%- trim(string) %>
```

### strip_html

Supprime toutes les balises HTML d'une chaîne.

``` js
<%- strip_html(string) %>
```

**Exemples :**

``` js
<%- strip_html('It's not <b>important</b> anymore!') %>
// It's not important anymore!
```

### titlecase

Transforme une chaîne pour avoir une majuscule à chaque mot qui n'est pas un déterminant.

``` js
<%- titlecase(string) %>
```

**Exemples :**

``` js
<%- titlecase('this is an apple') %>
# This is an Apple
```

### markdown

Traite une chaîne en Markdown.

``` js
<%- markdown(str) %>
```

**Examples:**

``` js
<%- markdown('mettez-moi en **gras**') %>
// mettez-moi en <strong>gras</strong>
```

### render

Traite une chaîne avec un moteur au choix.

``` js
<%- render(str, engine, [options]) %>
```

### word_wrap

Ajuste le texte pour tenir dans des lignes de `length` caractères. Par défaut, `length` correspond à 80.

``` js
<%- word_wrap(str, [length]) %>
```

**Exemples :**

``` js
<%- word_wrap('Once upon a time', 8) %>
// Once upon\n a time
```

### truncate

Tronque le text après `length`.

``` js
<%- truncate(text, length) %>
```

**Exemples :**

``` js
<%- truncate('Once upon a time in a world far far away', 16) %>
// Once upon a time
```

## Modèles

### partial

Charge d'autres fichiers de modèles. Vous pouvez définir des variables locales avec `locals`.

``` js
<%- partial(layout, [locals], [options]) %>
```

Option | Description | Par défaut
--- | --- | ---
`cache` | Contenus du cache (utiliser le cache des fragments) | `false`
`only` | Variables locales stricte. Utiliser uniquement les variables définies dans `locals` dans les modèles. | `false`

### fragment_cache

Met en cache le contenu dans un fragment. Cela sauvegarde les contenus dans un fragment et sert le cache lorsque la requête suivante est effectuée.

``` js
<%- fragment_cache(id, fn);
```

**Exemples :**

``` js
<%- fragment_cache('header', function(){
  return '<header></header>';
}) %>
```

## Date et heure

### date

Insère la date formattée. `date` peut être l'heure UNIX, une chaîne ISO, un objet de date, ou un objet [Moment.js]. `format` correspond au réglage `date_format` par défaut.

``` js
<%- date(date, [format]) %>
```

**Exemples :**

``` js
<%- date(Date.now()) %>
// 2013-01-01

<%- date(Date.now(), 'YYYY/M/D') %>
// Jan 1 2013
```

### date_xml

Insère la date au format XML. `date` peut être l'heure UNIX, une chaîne ISO, un objet de date, ou un objet [Moment.js].

``` js
<%- date_xml(date) %>
```

**Exemples :**

``` js
<%- date_xml(Date.now()) %>
// 2013-01-01T00:00:00.000Z
```

### time

Insère l'heure formattée. `date` peut être l'heure UNIX, une chaîne ISO, un objet de date, ou un objet [Moment.js]. `format` correspond au réglage `time_format` par défaut.

``` js
<%- time(date, [format]) %>
```

**Exemples :**

``` js
<%- time(Date.now()) %>
// 13:05:12

<%- time(Date.now(), 'h:mm:ss a') %>
// 1:05:12 pm
```

### full_date

Insère la date et l'heure formattée. `date` peut être l'heure UNIX, une chaîne ISO, un objet de date, ou un objet [Moment.js]. `format` correspond au réglage `date_format + time_format` par défaut.


``` js
<%- full_date(date, [format]) %>
```

**Exemples :**

``` js
<%- full_date(new Date()) %>
// Jan 1, 2013 0:00:00

<%- full_date(new Date(), 'dddd, MMMM Do YYYY, h:mm:ss a') %>
// Tuesday, January 1st 2013, 12:00:00 am
```

### moment

Bibliothèque [Moment.js].

## Liste

### list_categories

Insère une liste de toutes les catégories.

``` js
<%- list_categories([options]) %>
```

Option | Description | Par défaut
--- | --- | ---
`orderby` | Ordre des catégories | name
`order` | Ordre de tri. `1`, `asc` pour un tri ascendant ; `-1`, `desc` pour un tri descendant | 1
`show_count` | Affiche le nombre de posts dans chaque catégorie | true
`style` | Style d'affichage de la liste des catégories. `list` affiche les catégories dans une liste non ordonnée.  | list
`separator` | Séparateur entre les catégories (ne fonctionne que si `style` n'est pas `list`) | ,
`depth` | Niveau des catégories à afficher. `0` affiche toutes les catégories ainsi que les sous-catégories ; `-1` est similaire à `0` mais affichée de manière plate ; `1` n'affiche que les catégories de premier niveau. | 0
`class` | Nom de classe de la liste des catégories. | category
`transform` | La fonction qui change l'affichage du nom des catégories. |

### list_tags

Insère une liste de toutes les étiquettes.

``` js
<%- list_tags([options]) %>
```

Option | Description | Par défaut
--- | --- | ---
`orderby` | L'ordre des étiquettes | name
`order` | L'ordre de tri. `1`, `asc` pour un tri ascendant; `-1`, `desc` pour un tri descendant | 1
`show_count` | Afficher le nombre de posts de chaque étiquette | true
`style` | Style d'affichage de la liste des étiquettes. `list` affiche les étiquettes dans une liste non ordonnée. | list
`separator` | Séparater entre les étiquettes (ne fonctionne que si `style` n'est pas `list`) | ,
`class` | Nom de classe de la liste des étiquettes. | tag
`transform` | La fonction qui change l'affichage du nom des étiquettes. |
`amount` | Le nombre d'étiquettes à afficher (0 = illimité) | 0

### list_archives

Insère une liste des archives.

``` js
<%- list_archives([options]) %>
```

Option | Description | Par défaut
--- | --- | ---
`type` | Type. This value can be `yearly` or `monthly`. | monthly
`order` | Sort of order. `1`, `asc` for ascending; `-1`, `desc` for descending | 1
`show_count` | Display the number of posts for each archive | true
`format` | Date format | MMMM YYYY
`style` | Style to display the archive list. `list` displays archives in an unordered list.  | list
`separator` | Separator between archives. (Only works if `style` is not `list`) | ,
`class` | Class name of archive list. | archive
`transform` | The function that changes the display of archive name. |

### list_posts

Insère une liste de posts.

``` js
<%- list_posts([options]) %>
```

Option | Description | Par défaut
--- | --- | ---
`orderby` | Order of posts | date
`order` | Sort of order. `1`, `asc` for ascending; `-1`, `desc` for descending | 1
`style` | Style to display the post list. `list` displays posts in an unordered list.  | list
`separator` | Separator between posts. (Only works if `style` is not `list`) | ,
`class` | Class name of post list. | post
`amount` | The number of posts to display (0 = unlimited) | 6
`transform` | The function that changes the display of post name. |

### tagcloud

Insère un nuage d'étiquettes.

``` js
<%- tagcloud([tags], [options]) %>
```

Option | Description | Par défaut
--- | --- | ---
`min_font` | Taille de police minimale | 10
`max_font` | Taille de police maximale | 20
`unit` | Unité de la taille de police | px
`amount` | Nombre total d'étiquettes | 40
`orderby` | Ordre des étiquettes | name
`order` | Ordre de tri. `1`, `asc` pour un tri ascendant ; `-1`, `desc` pour un tri descendant | 1
`color` | Met en couleur le nuage d'étiquettes | false
`start_color` | Couleur de départ. Vous pouvez utiliser des codes hexadécimaux (`#b700ff`), rgba (`rgba(183, 0, 255, 1)`), hsla (`hsla(283, 100%, 50%, 1)`) ou des [mots-clés de couleur]. Cette option fonctionne uniquement lorsque `color` est activé. |
`end_color` | Couleur de fin. Vous pouvez utiliser des codes hexadécimaux (`#b700ff`), rgba (`rgba(183, 0, 255, 1)`), hsla (`hsla(283, 100%, 50%, 1)`) ou des [mots-clés de couleur]. Cette option fonctionne uniquement lorsque `color` est activé. |

## Divers

### paginator

Insère une pagination.

``` js
<%- paginator(options) %>
```

Option | Description | Par défaut
--- | --- | ---
`base` | URL de base | /
`format` | Format de l'URL | page/%d/
`total` | Le nombre de pages | 1
`current` | La page actuelle | 0
`prev_text` | The link text of previous page. Works only if `prev_next` is set to true. | Prev
`next_text` | The link text of next page. Works only if `prev_next` is set to true. | Next
`space` | The space text | &hellp;
`prev_next` | Display previous and next links | true
`end_size` | The number of pages displayed on the start and the end side | 1
`mid_size` | The number of pages displayed between current page, but not including current page | 2
`show_all` | Display all pages. If this is set true, `end_size` and `mid_size` will not works. | false

### search_form

Insère un champ de recherche Google.

``` js
<%- search_form(options) %>
```

Option | Description | Default
--- | --- | ---
`class` | The class name of form | search-form
`text` | Search hint word | Search
`button` | Display search button. The value can be a boolean or a string. When the value is a string, it'll be the text of the button. | false

### number_format

Formate un nombre.

``` js
<%- number_format(number, [options]) %>
```

Option | Description | Par défaut
--- | --- | ---
`precision` | La précision du nombre. La valeur peut être `false` ou un entier non négatif. | false
`delimiter` | Le séparateur des milliers | ,
`separator` | Le séparateur de la partie entière et décimale. | .

**Exemples :**

``` js
<%- number_format(12345.67, {precision: 1}) %>
// 12,345.68

<%- number_format(12345.67, {precision: 4}) %>
// 12,345.6700

<%- number_format(12345.67, {precision: 0}) %>
// 12,345

<%- number_format(12345.67, {delimiter: ''}) %>
// 12345.67

<%- number_format(12345.67, {separator: '/'}) %>
// 12,345/67
```

### open_graph

Insère des données [Open Graph].

``` js
<%- open_graph([options]) %>
```

Option | Description | Default
--- | --- | ---
`title` | Titre de la page (`og:title`) | `page.title`
`type` | Type de page (`og:type`) | blog
`url` | URL de la page (`og:url`) | `url`
`image` | Couverture de la page (`og:image`) | Première image dans le contenu
`site_name` | Nom du site (`og:site_name`) | `config.title`
`description` | Description de la page (`og:desription`) | Extrait de la page ou les 200 premiers caractères du contenu
`twitter_card` | Type de carte Twitter (`twitter:card`) | summary
`twitter_id` | Identifiant Twitter (`twitter:creator`) |
`twitter_site` | Site Twitter (`twitter:site`) |
`google_plus` | Lien vers le profil Google+ |
`fb_admins` | Identifiant d'administrateur Facebook |
`fb_app_id` | ID d'application Facebook |

### toc

Analyse tous les titres (h1~h6) dans le contenu et tnsère une table des matières.

``` js
<%- toc(str, [options]) %>
```

Option | Description | Par défaut
--- | --- | ---
`class` | Nom de classe | toc
`list_number` | Affiche les numéros dans la liste | true

**Exemples :**

``` js
<%- toc(page.content) %>
```

[mots-clés de couleur]: http://www.w3.org/TR/css3-color/#svg-color
[Moment.js]: http://momentjs.com/
[Open Graph]: http://ogp.me/
