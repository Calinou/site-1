title: Thèmes
---
Il est facile de créer un thème pour Hexo - vous avez juste à créer un nouveau dossier. Pour commencer à utiliser votre thème, modifiez le paramètre `theme` dans le `_config.yml` de votre site. Un thème peut avoir la structure suivante :

``` plain
.
├── _config.yml
├── languages
├── layout
├── scripts
└── source
```

### _config.yml

Le fichier de configuration du thème. Vous n'avez pas besoin de redémarrer le serveur après l'avoir modifié.

### languages

Le dossier des langues. Jetez un oeil à [localization (i18n)](localization.html) pour plus d'informations.

### layout

Le dossier des mises en page. Ce dossier contient les fichiers modèle du thème, qui définissent l'apparence de votre site. Par défaut, Hexo utilise le moteur de templates [Swig]. Vous pouvez installer des extensions afin de prendre en charge des moteurs alternatifs comme [EJS], [Haml] ou encore [Jade]. Hexo choisit le moteur de templates à utiliser en fonction de l'extension du fichier du modèle. Par exemple :

``` plain
layout.ejs   - utilise EJS
layout.swig  - utilise Swig
```

Pour plus d'informations, consultez [templates](templates.html).

### scripts

Le dossier des scripts. Les fichiers JavaScript dans ce dossier seront chargés lorsque Hexo démarre. Pour plus d'informations, consultez [plugins](plugins.html).

### source

Le dossier source. Les "contenus" comme les fichiers CSS et JavaScript de votre site doivent être placés ici. Hexo ignore les fichiers cachés ou encore les fichiers et dossiers dont le nom commence par un `_` (underscore).

Les fichiers qui peuvent être rendus sont traités et sauvegardés dans le dossier `public`. Les autres fichiers sont copiés directement dans le dossier `public`.

### Publication

Une fois votre thème terminé, vous pouvez le publier sur la [liste de thèmes](/themes). Avant publication, vous devrez lancer les [tests unitaires sur les thèmes](https://github.com/hexojs/hexo-theme-unit-test) et vous assurer que tout fonctionne. Les étapes pour publier un thème sont très similaires à celles que pour [mettre à jour la documentation](contributing.html#Updating_Documentation).

1. Forkez [hexojs/site]
2. Clonez le dépôt sur votre PC et installez les dépendances.

    {% code %}
    $ git clone https://github.com/<username>/site.git
    $ cd site
    $ npm install
    {% endcode %}

3. Modifiez `source/_data/themes.yml` et ajoutez votre thème. Par exemple :

    {% code %}
    - name: landscape
      description: A brand new default theme for Hexo.
      link: https://github.com/hexojs/hexo-theme-landscape
      preview: http://hexo.io/hexo-theme-landscape
      tags:
        - official
        - responsive
        - widget
        - two_column
        - one_column
    {% endcode %}

4. Ajoutez une capture d'écran (avec le même nom que le thème) dans `source/themes/screenshots`. Il doit s'agir d'un PNG de 800*500 pixels.
5. Poussez la branche.
6. Créez un pull request et décrivez les modifications effectuées.

[EJS]: https://github.com/hexojs/hexo-renderer-ejs
[Swig]: http://paularmstrong.github.com/swig/
[Haml]: https://github.com/hexojs/hexo-renderer-haml
[Jade]: https://github.com/hexojs/hexo-renderer-jade
[hexojs/site]: https://github.com/hexojs/site
