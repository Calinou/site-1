title: Extensions
---
Hexo dispose d'un puissant système d'extensions, ce qui le rend facile à étendre sans avoir à modifier le code source du module principal. Il y a deux types d'extensins dans Hexo :

### Script

Si votre code est simple, il est recommandé d'utiliser un script. Tout ce que vous avez à faire, c'est mettre vos fichiers JavaScript dans le dossier `scripts` et ils seront chargés une fois Hexo initialisé.

### Extension

Si votre code est plus complexe ou vous désirez le publier sur le registre NPM, il est recommandé d'utiliser une extension. Tout d'abord, créez un dossier dans le répertoire `node_modules`. Le nom du dossier doit commencer par `hexo-` afin qu'il soit chargé par Hexo.

Le dossier doit contenir au moins 2 fichiers : un d'entre eux est le programme principal, tandis que le `package.json` décrit le but et les dépendances de l'extension.

``` plain
.
├── index.js
└── package.json
```

Vous devriez décrire au moins `name`, `version`, `main` dans `package.json`. Par exemple :

``` json package.json
{
  "name": "hexo-my-plugin",
  "version": "0.0.1",
  "main": "index"
}
```

### Tools

Vous pouvez utiliser les outils officiels fournis par Hexo afin d'accélérer le développement :

- [hexo-fs]：Entrée/sortie fichier
- [hexo-util]：Utilitaires
- [hexo-i18n]：Localisation (i18n)
- [hexo-pagination]：Générer des données de pagination

### Publication

Une fois votre extension réalisée, vous pouvez la publier sur la [liste des extensions](/plugins) afin que davantage de personnes l'utilisent. Les étapes afin de publier une extension sont très similaires à celles pour [mettre à jour la documentation](contributing.html#Updating_Documentation).

1. Forkez [hexojs/site]
2. Clonez le dépôt sur votre PC et installez les dépendances.

    {% code %}
    $ git clone https://github.com/<username>/site.git
    $ cd site
    $ npm install
    {% endcode %}

3. Modifiez `source/_data/_plugins.yml` et ajoutez votre extension. Par exemple :

    {% code %}
    - name: hexo-server
      description: Server module for Hexo.
      link: https://github.com/hexojs/hexo-server
      tags:
        - official
        - server
        - console
    {% endcode %}

4. Poussez la branche.
5. Créez une demande de pull et décrivez vos modifications.

[hexo-fs]: https://github.com/hexojs/hexo-fs
[hexo-util]: https://github.com/hexojs/hexo-util
[hexo-i18n]: https://github.com/hexojs/hexo-i18n
[hexo-pagination]: https://github.com/hexojs/hexo-pagination
[hexojs/site]: https://github.com/hexojs/site
