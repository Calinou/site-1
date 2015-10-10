title: Permaliens
---
Vous pouvez spécifier les permaliens pour votre site dans `_config.yml` ou dans le front-matter de votre post.

### Variables

En plus des variables suivantes, vous pouvez utiliser n'importe quels attributs dans votre permalien.

Variable | Description
--- | ---
`:year` | Année de publication des posts (4 chiffres)
`:month` | Mois de publication des posts (2 chiffres)
`:i_month` | Mois de publication des posts (sans le zéro non significatif)
`:day` | Jour de publication des posts (2 chiffres)
`:i_day` | Jour de publication des posts (sans le zéro non significatif)
`:title` | Nom de fichier
`:id` | ID du post
`:category` | Catégories. Si le post n'a pas de catégorie, alors cette variable correspondra au réglage `default_category`.

Vous pouvez définir la valeur par défaut de chaque variable dans le permalien dans le réglage `permalink_defaults` :

``` yaml
permalink_defaults:
  lang: en
```

### Exemples

Admettons un post nommé `hello-world.md` dans le dossier `source/_posts` avec le contenu suivant.

``` yaml
title: Hello World
date: 2013-07-14 17:01:34
categories:
- foo
- bar
```

Setting | Result
--- | ---
`:year/:month/:day/:title/` | 2013/07/14/hello-world
`:year-:month-:day-:title.html` | 2013-07-14-hello-world.html
`:category/:title` | foo/bar/hello-world

### Support multilingue

Pour créer un site multilingue, vous pouvez modifier les réglages `new_post_name` et `permalink` :

``` yaml
new_post_name: :lang/:title.md
permalink: :lang/:title/
```

Lorsque vous créez un nouveau post, le post sera sauvegardé dans :

``` bash
$ hexo new "Hello World" --lang tw
# => source/_posts/tw/Hello-World.md
```

et l'URL sera :

``` plain
http://localhost:4000/tw/hello-world/
```
