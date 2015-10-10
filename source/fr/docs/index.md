title: Documentation
---
Bienvenue sur la documentation d'Hexo. Si vous rencontrez un problème lors de l'utilisation d'Hexo, jetez un oeil à notre guide de [résolution des problèmes](troubleshooting.html), créez une demande sur [GitHub](https://github.com/hexojs/hexo/issues) ou créez un fil sur le [groupe Google](https://groups.google.com/group/hexo).

## Qu'est-ce qu'Hexo ?

Hexo est un framework de blog simple, rapide et puissant. Vous écrivez vos posts en [Markdown](http://daringfireball.net/projects/markdown/) (ou d'autres langages) et Hexo génère des fichiers statiques avec un joli thème en quelques secondes seulement.

## Installation

Installer Hexo ne prend que quelques minutes. Si vous rencontrez un problème et ne pouvez pas trouver le solution ici, veuillez [soumettre une demande GitHub](https://github.com/hexojs/hexo/issues) et j'essaierai de la résoudre.

### Pré-requis

Installer Hexo, c'est plutôt facile. Cependant, vous devez avoir deux logiciels installés sur votre PC :

- [Node.js](http://nodejs.org/)
- [Git](http://git-scm.com/)

Si votre ordinateur a déjà ces logiciels, félicitations ! Installez simplement Hexo à l'aide de npm :

``` bash
$ npm install -g hexo-cli
```

Si ce n'est pas le cas, veuillez suivre les instructions suivantes afin d'installer les pré-requis.

{% note warn Pour les utilisateurs d'OS X %}
Vous pouvez rencontrer certains problèmes lors de la compilation. Veuillez installer Xcode depuis l'App Store d'abord. Une fois Xcode installé, ouvrez-le et allez dans **Préférences -> Téléchargements -> Outils de ligne de commande -> Installer** afin d'installer les outils en ligne de commande.
{% endnote %}

### Installer Git

- Windows : Téléchargez et installez [Git](https://git-scm.com/download/win).
- OS X : Installez-le à l'aide d'[Homebrew](http://mxcl.github.com/homebrew/), [MacPorts](http://www.macports.org/) ou [Installer](http://sourceforge.net/projects/git-osx-installer/).
- GNU/Linux (Ubuntu, Debian) : `sudo apt-get install git-core`
- GNU/Linux (Fedora, Red Hat, CentOS) : `sudo yum install git-core`

### Installer Node.js

La meilleure façon d'installer Node.js est d'utiliser [nvm](https://github.com/creationix/nvm).

cURL :

``` bash
$ curl https://raw.github.com/creationix/nvm/master/install.sh | sh
```

wget :

``` bash
$ wget -qO- https://raw.github.com/creationix/nvm/master/install.sh | sh
```

Une fois nvm installé, redémarrez le terminal et lancez la commande suivante afin d'installer Node.js.

``` bash
$ nvm install 0.12
```

Alternativement, téléchargez et lancez [l'installateur](http://nodejs.org/).

### Installer Hexo

Une fois que vous avez satisfait les pré-requis, vous pouvez installer Hexo avec npm.

``` bash
$ npm install -g hexo-cli
```
