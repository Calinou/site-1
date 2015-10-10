title: Génération
---
Générer des fichiers statiques à l'aide de Hexo est simple et rapide.

``` bash
$ hexo generate
```

### Surveiller les modifications sur les fichiers

Hexo peut surveiller les modifications effectuées sur les fichiers et régénérer les fichiers automatiquement. Hexo compare les sommes de contrôle SHA1 et ne réécrit que si nécessaire.

``` bash
$ hexo generate --watch
```

### Déploiement après génération

Afin de déployer après avoir généré le site, vous pouvez utiliser une de ces deux commandes. Les deux commandes font strictement la même chose.

``` bash
$ hexo generate --deploy
$ hexo deploy --generate
```
