title: Déploiement
---
Hexo vous donne accès à une méthode facile et rapide pour le déploiement. Vous n'avez besoin que d'une commande afin de déployer votre site vers un ou des serveurs.

``` bash
$ hexo deploy
```

Avant de commencer, vous devez modifier des réglages dans `_config.yml`. Un réglage de déploiement valide doit obligatoirement avec un champ `type` . Par exemple :

``` yaml
deploy:
  type: git
```

Vous pouvez utiliser plusieurs outils de déploiement. Hexo les exécutera un à la fois, dans l'ordre (de haut en bas).
``` yaml
deploy:
- type: git
  repo:
- type: heroku
  repo:
```

## Git

Installez [hexo-deployer-git].

``` bash
$ npm install hexo-deployer-git --save
```

Modifiez les réglages.

``` yaml
deploy:
  type: git
  repo: <URL du dépôt>
  branch: [branche]
  message: [message]
```

Option | Description
--- | ---
`repo` | L'adresse URL du dépot GitHub
`branch` | Le nom de la branch. L'outil de déploiement détectera la branche automatiquement si vous utilisez GitHub ou GitCafe.
`message` | Personnaliser le message de *commit* (par défaut : `Site updated: {% raw %}{{ now('YYYY-MM-DD HH:mm:ss') }}{% endraw %}`)

## Heroku

Installez [hexo-deployer-heroku].

``` bash
$ npm install hexo-deployer-heroku --save
```

Modifiez les réglages.

``` yaml
deploy:
  type: heroku
  repo: <URL du dépôt>
  message: [message]
```

Option | Description
--- | ---
`repo`, `repository` | L'adresse URL du dépôt Heroku
`message` | Personnaliser le message de *commit* (par défaut : `Site updated: {% raw %}{{ now('YYYY-MM-DD HH:mm:ss') }}{% endraw %}`)

## Rsync

Installez [hexo-deployer-rsync].

``` bash
$ npm install hexo-deployer-rsync --save
```

Modifiez les réglages.

``` yaml
deploy:
  type: rsync
  host: <host>
  user: <user>
  root: <root>
  port: [port]
  delete: [true|false]
  verbose: [true|false]
  ignore_errors: [true|false]
```

Option | Description | Default
--- | --- | ---
`host` | L'adresse de l'hôte distant |
`user` | Le nom d'utilisateur |
`root` | Le répertoire racine de l'hôte distant |
`port` | Le port | 22
`delete` | Supprimer les anciens fichiers sur l'hôte distant | true
`verbose` | Afficher les messages verbeux | true
`ignore_errors` | Ignorer les erreurs | false

## OpenShift

Installez [hexo-deployer-openshift].

``` bash
$ npm install hexo-deployer-openshift --save
```

Modifiez les réglages.

``` yaml
deploy:
  type: openshift
  repo: <repository url>
  message: [message]
```

Option | Description
--- | ---
`repo` | L'adresse URL du dépôt OpenShift
`message` | Personnaliser le message de *commit* (par défaut : `Site updated: {% raw %}{{ now('YYYY-MM-DD HH:mm:ss') }}{% endraw %}`)

## FTPSync

Installez [hexo-deployer-ftpsync].

``` bash
$ npm install hexo-deployer-ftpsync --save
```

Modifiez les réglages.

``` yaml
deploy:
  type: ftpsync
  host: <hôte>
  user: <nom d'utilisateur>
  pass: <mot de passe>
  remote: [chemin]
  port: [port]
  ignore: [ignorer]
  connections: [connections]
  verbose: [true|false]
```

Option | Description | Default
--- | --- | ---
`host` | L'adresse de l'hôte distant |
`user` | Nom d'utilisateur |
`pass` | Mot de passe |
`remote` | Répertoire racine de l'hôte distant | `/`
`port` | Port | 21
`ignore` | Ignorer des fichiers sur l'hôte ou le serveur distant |
`connections` | Nombre de connexions | 1
`verbose` | Afficher les messages verbeux | false

## Autres méthodes

Tous les fichiers générés sont sauvegardés dans le dossier `public`. Vous pouvez les copier où vous voulez.

[hexo-deployer-git]: https://github.com/hexojs/hexo-deployer-git
[hexo-deployer-heroku]: https://github.com/hexojs/hexo-deployer-heroku
[hexo-deployer-rsync]: https://github.com/hexojs/hexo-deployer-rsync
[hexo-deployer-openshift]: https://github.com/hexojs/hexo-deployer-openshift
[hexo-deployer-ftpsync]: https://github.com/hexojs/hexo-deployer-ftpsync
