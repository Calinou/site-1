title: Commandes
---
## init

``` bash
$ hexo init [dossier]
```

Intialise un site Web. Si `dossier` n'est pas précisé, Hexo mettra en place le site Web dans le répertoire courant.

## new

``` bash
$ hexo new [mise en page] <titre>
```

Crée un nouvel article. Si `mise en page` n'est pas précisé, Hexo utilisera le `default_layout` depuis [_config.yml](configuration.html). Si le `titre` contient des espaces, mettez des guillemets autour.

## generate

``` bash
$ hexo generate
```

Génère des fichiers statiques.

Option | Description
--- | ---
`-d`, `--deploy` | Déployer après la fin de la génération
`-w`, `--watch` | Surveiller les modifcations de fichiers

## publish

``` bash
$ hexo publish [mise en page] <nom de fichier>
```

Publie un brouillon.

## server

``` bash
$ hexo server
```

Démarre un serveur local. Par défaut, il est situé à l'adresse `http://localhost:4000/`.

Option | Description
--- | ---
`-p`, `--port` | Écraser le port par défaut
`-s`, `--static` | Ne servir que des fichiers statiques
`-l`, `--log` | Activer la journalisation. Écraser le format de journalisation.

## deploy

``` bash
$ hexo deploy
```

Déploie votre site.

Option | Description
--- | ---
`-g`, `--generate` | Générer avant déploiement

## render

``` bash
$ hexo render <fichier1> [fichier2] ...
```

Traite des fichiers.

Option | Description
--- | ---
`-o`, `--output` | Destination de sortie

## migrate

``` bash
$ hexo migrate <type>
```

[Migre](migration.html) du contenu depuis un autre système de blog.

## clean

``` bash
$ hexo clean
```

Supprime le fichier de cache (`db.json`) ainsi que les fichiers générés (`public`).

## list

``` bash
$ hexo list <type>
```

Liste toutes les routes.

## version

``` bash
$ hexo version
```

Affiche les informations de version.

## Options

### Mode sans échec

``` bash
$ hexo --safe
```

Désactive le chargement des scripts et extensions. Essayez ceci si vous rencontrez des problèmes après avoir installé une nouvelle extension.

### Mode débogage

``` bash
$ hexo --debug
```

Journalise les messages verbeux dans le terminal ainsi que dans `debug.log`. Essayez ceci si vous rencontrez des problèmes avec Hexo. Si vous voyez des erreurs, veuillez [créer un rapport de bogue sur GitHub](https://github.com/hexojs/hexo/issues/new).

### Mode silencieux

``` bash
$ hexo --silent
```

Désactive toute sortie dans le terminal.

### Persnnaliser le chemin vers le fichier de configuration

``` bash
$ hexo --config custom.yml
```

Utilise un fichier de configuration personnalisé (au lieu de `_config.yml`).

### Afficher les brouillons

``` bash
$ hexo --draft
```

Affiche les posts "brouillons" (stockés dans le dossier `source/_drafts`).

### Personnaliser le CWD

``` bash
$ hexo --cwd /chemin/vers/répertoire/courant
```

Personnalise le chemin vers le répertoire courant.
