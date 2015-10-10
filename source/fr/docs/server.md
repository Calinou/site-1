title: Serveur
---
## [hexo-server]

Le serveur a été séparé du module principal dans Hexo 3. Vous devez installer [hexo-server] avant de l'utiliser.

``` bash
$ npm install hexo-server --save
```

Une fois le serveur installé, lancez la commande suivante pour démarrer le serveur. Votre site Web sera à l'adresse `http://localhost:4000` par défaut. Lorsque le serveur est en marche, Hexo va automatiquement mettre à jour les fichiers lorsque c'est nécessaire ; vous n'avez pas besoin de redémarrer le serveur.

``` bash
$ hexo server
```

Si vous voulez modifier le port utilisé ou rencontrez une erreur `EADDRINUSE`, vous pouvez utiliser l'option `-p` afin d'utiliser un autre port.

``` bash
$ hexo server -p 5000
```

### Mode statique

En mode statique, seuls les fichiers dans le dossier `public` seront servis et la surveillance des fichiers est désactivée. Vous devez lancer `hexo generate` avant de démarrer le serveur. Souvent utilisé en production.

``` bash
$ hexo server -s
```

### IP personnalisée

Hexo lance le serveur sur `0.0.0.0` par défaut. Vous pouvez écraser le réglage d'adresse IP par défaut.

``` bash
$ hexo server -i 192.168.1.1
```

## Pow

[Pow] est un serveur Rack facile à utiliser pour OS X.

### Installation

``` bash
$ curl get.pow.cx | sh
```

### Mise en route

Créez un lien symbolique dans `~/.pow`

``` bash
$ cd ~/.pow
$ ln -s /path/to/myapp
```

Votre site sera opérationnel à l'adresse `http://myapp.dev`. L'URL est basée sur le nom de votre lien symbolique.

[hexo-server]: https://github.com/hexojs/hexo-server
[Pow]: http://pow.cx/
