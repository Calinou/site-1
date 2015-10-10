title: Fichiers de données
---
Parfois, vous pouvez avoir besoin d'utiliser des données dans des modèles qui ne sont pas dans des posts, ou vous désirez réutiliser ces données. Dans ce cas, vous pouvez utiliser les "**fichiers de données**" introduits dans Hexo 3. Cette fonctionnalité charge des fichiers YAML ou JSON dans le dossier `source/_data`, et vous pourrez en servir sur votre site.

Par exemple, ajoutez un fichier `menu.yml` dans le dossier `source/_data`.

``` yaml
Home: /
Gallery: /gallery/
Archives: /archives/
```

Et vous pouvez les utiliser dans des modèles :

```
{% for link in site.data.menu %}
  <a href="{{ link }}">{{ loop.key }}</a>
{% endfor %}
```
