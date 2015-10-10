title: Front-matter
---
La front-matter est un bloc de YAML ou de JSON au début d'un fichier qui est utilisé afin de configurer des réglages relatifs à vos écrits. La front-matter est terminée par trois tirets lorsqu'elle est écrite en YAML ou trois points-virgules lorsqu'elle est écrite en JSON.

**YAML**
``` yaml
title: Hello World
date: 2013/7/13 20:46:25
---
```

**JSON**
``` json
"title": "Hello World",
"date": "2013/7/13 20:46:25"
;;;
```

### Réglages ainsi que leurs valeurs par défaut

Réglage | Description | Par défaut
--- | --- | ---
`layout` | Mise en page |
`title` | Titre |
`date` | Date de publication | Date de création du fichier
`updated` | Date de mise à jour | Date de mise à jour du fichier
`comments` | Active les commentaires pour le post | true
`tags` | Étiquettes (non disponible pour les pages) |
`categories` | Catégories (non disponible pour les pages) |
`permalink` | Écrase le permalien par défaut pour le post |

#### Catégories et étiquettes

Les catégories et les étiquettes sont prises en charge uniquement pour les posts. Les catégories s'appliquent aux posts dans l'ordre, ce qui crée une hiérarchie de classifications et de sous-classifications ; les étiquettes sont toutes au même niveau et leur ordre n'a pas d'importance.

**Exemple**

``` yaml
categories:
- Sports
- Baseball
tags:
- Injury
- Fight
- Shocking
```
