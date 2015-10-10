title: Migration
---
## RSS

Tout d'abord, installez l'extension `hexo-migrator-rss`.

``` bash
$ npm install hexo-migrator-rss --save
```

Une fois l'extension installée, lancez la commande suivante afin de migrer tous les posts depuis RSS. `source` peut être le chemin vers un fichier ou une URL.

``` bash
$ hexo migrate rss <source>
```

## Jekyll

Déplacez tous les fichiers dans le dossier Jekyll `_posts` vers le dossier `source/_posts`.

Modifiez le réglage `new_post_name` dans `_config.yml`:

``` yaml
new_post_name: :year-:month-:day-:title.md
```

## Octopress

Déplacez tous les fichiers dans le dossier Octopress `source/_posts` vers le dossier `source/_posts`.

Modifiez le réglage `new_post_name` dans `_config.yml`:

``` yaml
new_post_name: :year-:month-:day-:title.md
```

## WordPress

Tout d'abord, installez l'extension `hexo-migrator-wordpress`.

``` bash
$ npm install hexo-migrator-wordpress --save
```

Exportez votre site WordPress en allant dans "Outils" → "Exporter" → "WordPress" dans le tableau de bord WordPress (pour plus d'informations, consultez la [page de support WordPress](http://en.support.wordpress.com/export/) dédiée à cette fonction).

Maintenant, lancez cette commande :

``` bash
$ hexo migrate wordpress <source>
```

`source` est le chemin ou l'URL vers le fichier d'exportation WordPress.

## Joomla

Tout d'abord, installez l'extension `hexo-migrator-joomla`.

```bash
$ npm install hexo-migrator-joomla --save
```

Exportez vos articles Joomla en utilisant le composant [J2XML](http://extensions.joomla.org/extensions/migration-a-conversion/data-import-a-export/12816?qh=YToxOntpOjA7czo1OiJqMnhtbCI7fQ%3D%3D).

Maintenant, lancez cette commande :

```bash
$ hexo migrate joomla <source>
```

`source` est le chemin ou l'URL vers le fichier d'exportation Joomla.
