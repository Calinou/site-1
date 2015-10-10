title: Mise en route
---
Une fois Hexo installé, lancez les commandes suivantes pour initialiser Hexo dans le dossier cible `<folder>`.

``` bash
$ hexo init <folder>
$ cd <folder>
$ npm install
```

Une fois initialisé, voici à quoi ressemblera votre dossier de projet :

``` plain
.
├── _config.yml
├── package.json
├── scaffolds
├── scripts
├── source
|   ├── _drafts
|   └── _posts
└── themes
```

### _config.yml

Il s'agit du fichier de [configuration](configuration.html) de votre site. Vous pouvez configurer la plupart des réglages de votre site dans ce fichier.

### package.json

Les données d'application. Les moteurs de rendu [EJS](http://embeddedjs.com/), [Stylus](http://learnboost.github.io/stylus/) ainsi que [Markdown](http://daringfireball.net/projects/markdown/) sont installés par défaut. Si vous voulez, vous pouvez les désinstaller plus tard.

``` json package.json
{
  "name": "hexo-site",
  "version": "0.0.0",
  "private": true,
  "hexo": {
    "version": ""
  },
  "dependencies": {
    "hexo": "^3.0.0",
    "hexo-generator-archive": "^0.1.0",
    "hexo-generator-category": "^0.1.0",
    "hexo-generator-index": "^0.1.0",
    "hexo-generator-tag": "^0.1.0",
    "hexo-renderer-ejs": "^0.1.0",
    "hexo-renderer-stylus": "^0.2.0",
    "hexo-renderer-marked": "^0.2.4",
    "hexo-server": "^0.1.2"
  }
}
```

### scaffolds

Le dossier des [échafaudages](writing.html#Scaffolds). Lorsque vous créez un nouveau post, Hexo se base sur les échafaudages existants.

### scripts

Le dossier des [scripts](plugins.html#Scripts). Les scripts sont la manière la plus facile d'étendre Hexo. Les fichiers JavaScript situés dans ce dossier sont exécutés automatiquement.

### source

Le dossier source. C'est ici que vous mettez le contenu de votre site. Hexo ignore les fichiers cachés, ainsi que les fichiers ou dossiers dont le nom commence par un `_` (underscore) - à l'exception du dossier `_posts`. Les fichiers qui peuvent être rendus (comme le Markdown ou l'HTML) seront traités et copiés dans le dossier `public`, tandis que les autres fichiers seront tout simplement copiés.

### themes

Le dossier des [thèmes](themes.html). Hexo génère un site statique en combinant les contenus du site avec le thème.
