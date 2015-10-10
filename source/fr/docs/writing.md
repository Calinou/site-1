title: Écriture
---
Pour créer un nouveau post, vous pouvez lancer la commande suivante :

``` bash
$ hexo new [mise en page] <titre>
```

`post` est le `layout` (mise en page) par défaut, mais vous pouvez créer votre propre mise en page. Vous pouvez changer la mise en page par défaut en modifiant le réglage `default_layout` dans `_config.yml`.

### Mise en page

Il y a trois mises en page par défaut avec Hexo : `post`, `page` et `draft`. Chacun d'entre eux est sauvegardé vers un chemin différent. Les mises en pages personnalisées sont sauvegardées dans le dossier `source/_posts`.

Mise en page | Chemin
--- | ---
`post` | `source/_posts`
`page` | `source`
`draft` | `source/_drafts`

{% note tip Ne traitez pas mes posts ! %}
Si vous ne voulez pas que vos posts soient traités, définissez `layout: false` dans le front-matter.
{% endnote %}

### Nom de fichier

Par défaut, Hexo utilise le nom du post en tant que nom du fichier. Vous pouvez éditer le réglage `new_post_name` dans `_config.yml` afin de changer le nom de fichier par défaut. Par exemple `:year-:month-:day-:title.md` préfixera les noms de fichiers par la date de création du post. Vous pouvez utiliser les variables suivantes :

Variable | Description
--- | ---
`:title` | Titre du post (en minuscules, avec les espaces remplacées par des tirets)
`:year` | Année de création, par exemple `2015`
`:month` | Mois de création (avec zéro si nécessaire), par exemple `04`
`:i_month` | Mois de création (sans zéro si nécessaire), par exemple `4`
`:day` | Jour de création (avec zéro si nécessaire), par exemple `07`
`:i_day` | Jour de création (sans zéro si nécessaire), `7`

### Brouillons

Au début de cette page, nous avons mentionné une mise en page spéciale dans Hexo : `draft` (brouillon). Les posts avec cette mise en page sont sauvegardés dans le dossier `source/_drafts`. Vous pouvez utiliser la commande `publish` pour déplacer les brouillons dans le dossier `source/_posts`. Cette commande fonctionne d'une manière similaire à la commande `new`.

``` bash
$ hexo publish [mise en page] <titre>
```

Les brouillons ne sont pas affichés par défaut. Vous pouvez ajouter l'option `--draft` quand vous lancez Hexo ou activer le réglage `render_drafts` dans `_config.yml` afin de traiter les brouillons.

### Échafaudages

Lorsque Hexo crée des posts, il va construire des fichiers basés sur le fichier correspondant dans le dossier `scaffolds` (échafaudages). Par exemple :

``` bash
$ hexo new photo "Ma galerie"
```

Lorsque vous lancez cette commande, Hexo va essayez de trouver `photo.md` dans le dossier `scaffolds` et va construire le post en se basant sur ce modèle. Les variables suivantes sont accessibles dans les échafaudages :

Variable | Description
--- | ---
`layout` | Mise en page
`title` | Titre
`date` | Date de création du fichier
