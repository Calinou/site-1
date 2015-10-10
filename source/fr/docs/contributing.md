title: Contribuer
---
## Développement

Nous vous remercions de votre intérêt pour Hexo. Ce document vous aidera dans le processus de contribution.

### Avant de commencer

Veuillez suivre le guide de style suivant :

- Suivez le [guide de style JavaScript de Google](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml).
- Utilisez des tabulations "douces" de 2 espaces.
- Ne mettez pas de virgule en début de ligne.

### Workflow

1. Forkez [hexojs/hexo].
2. Clonez le dépôt sur votre PC et installez les dépendances.

    {% code %}
    $ git clone https://github.com/<username>/hexo.git
    $ cd hexo
    $ npm install
    $ git submodule update --init
    {% endcode %}

3. Créez une branche pour votre fonctionnalité.

    {% code %}
    $ git checkout -b new_feature
    {% endcode %}

4. Développez.
5. Poussez la branche :

    {% code %}
    $ git push origin new_feature
    {% endcode %}

6. Créez une demande de pull et décrivez vos modifications.

### Attention

- Ne modifiez pas le numéro de version dans `package.json`.
- Votre demande de pull ne sera fusionnée que lorsque tous les tests passent avec succès. N'oubliez pas de lancer les tests avant de soumettre votre demande.

    {% code %}
    $ npm test
    {% endcode %}

## Mettre à jour la documentation

La documentation d'Hexo est *open source* et vous pouvez trouver le code source dans [hexojs/site].

### Structure de travail

1. Forkez [hexojs/site]
2. Clonez le dépôt sur votre PC et installez les dépendances.

    {% code %}
    $ git clone https://github.com/<username>/site.git
    $ cd site
    $ npm install
    {% endcode %}

3. Commencez à modifier la documentation. Vous pouvez démarrer un serveur afin de visualiser vos modifications en direct.

    {% code %}
    $ hexo server
    {% endcode %}

4. Poussez la branche.
5. Créez une demande de pull et décrivez les modifications.

### Traduire

1. Ajouter un nouveau dossier delangue dans le dossier `source`. (Tout en minuscules)
2. Copiez les fichiers Markdown et modèle du dossier `source` vers le nouveu dossier de langue.
3. Ajoutez la nouvelle langue dans `source/_data/language.yml`.
4. Copiez `en.yml` dans `themes/navy/languages` et renommez-le vers le code de langue (tout en minuscules).

## Rapporter des problèmes

Lorsque vous rencontrez un problème lors de l'utilisation d'Hexo, vous pouvez trouver des solutions à des problèmes courants dans [Résolution des problèmes](troubleshooting.html) ou demandez-moi sur [GitHub](https://github.com/hexojs/hexo/issues) ou le [groupe Google](https://groups.google.com/group/hexo). Si vous ne pouvez pas trouver la réponse à votre question, veuillez créer une demande sur GitHub.

1. Représentez le problème en [mode débogage](commands.html#Mode_débogage).
2. Lancez `hexo version` et vérifiez les informations de version.    
3. Postez à la fois le message de débogage et les informations de version sur GitHub.

[hexojs/hexo]: https://github.com/hexojs/hexo
[hexojs/site]: https://github.com/hexojs/site
