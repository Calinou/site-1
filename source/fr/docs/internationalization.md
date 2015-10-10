title: Internationalisation (i18n)
---
Vous pouvez utiliser l'internationalisation afin de présenter votre site en différentes langues. Modifiez d'abord le réglage `language` dans `_config.yml`. Il s'agit de la langue par défaut. Vous pouvez également définir plusieurs langues afin de définir l'ordre des langues par défaut.

``` yaml
language: zh-tw

language:
- zh-tw
- en
```

### Fichiers de langue

Les fichiers de langue peuvent être des fichiers YAML ou JSON. Ils doivent être mis dans le dossier `languages` du thème. Vous pouvez utiliser le [format printf](https://github.com/alexei/sprintf.js) dans les fichiers de langue.

### Modèles

Utilisez les assistants `__` ou `_p` dans les modèles afin de récupérer les chaînes traduites. Le premier est utilisé au singulier, et le second au pluriel. Par exemple :

``` yaml en.yml
index:
  title: Home
  add: Add
  video:
    zero: No videos
    one: One video
    other: %d videos
```

``` js
<%= __('index.title') %>
// Home

<%= _p('index.video', 3) %>
// 3 videos
```

### Chemin

Vous pouvez définir la langue des pages dans le front-matter, ou modifier le réglage `i18n_dir` dans `_config.yml` afin d'activer la détection automatique.

``` yaml
i18n_dir: :lang
```

La valeur par défaut du réglage `i18n_dir` est `:lang`, ce qui sigifie qu'Hexo détectera la langue grâce au premier segment de l'URL. Par exemple :

``` plain
/index.html => en
/archives/index.html => en
/zh-tw/index.html => zh-tw
```

La chaîne ne sera servie en tant que langue uniquement lorsque le fichier de langue existe. Donc, `archives` dans `/archives/index.html` (l'exemple 2) ne sera pas servie en tant que langue.
