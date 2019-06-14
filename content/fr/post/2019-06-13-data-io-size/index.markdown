---
title: "Ecriture, lecture et taille des fichiers, quelle est la fonction la plus efficace"
summary: "Quel est le meilleur package ? readr, data.table, feather, fst,..."
author: [admin]
date: 2019-06-13 17:00:00
links:
- icon: github
  icon_pack: fab
  name: GitHub
  url: https://github.com/BioDataScience-Course/dataset_io_speed_size
projects:
- biodatascience
categories: ["R", "BioDataScience"]
tags: ["R", "BioDataScience"]
---

Lors d'une réunion au sein du laboratoire, la question suivante a été posé : `Quelle est la meilleure fonction pour écrire des jeux de données ?`. Cette question induit en réalité deux sous-questions. On s'intéresse à la **vitesse d'écriture** et la **taille du fichier**. 

Suite à cette première question, on a également voulu savoir : `Quelle est la meilleure fonction pour importer des données en local ?`. On s'intéresse évidement à la vitesse d'importation. En partant de l'idée que plus un fichier sera compressé au plus il sera lent à ouvrir. 

Je m'imagine déjà réaliser une multitude de benchmark afin d'en déterminer là ou les meilleurs fonctions. Je crée un dépot pour consigner toutes mes recherches 

- <https://github.com/BioDataScience-Course/dataset_io_speed_size>.

# Recherches bibliographiques

Mes réflexions ont été guidées par la lecture des sites suivants :

- vitesse d’écriture, vitesse de lecture et taille du jeu de données
    - <https://www.h2o.ai/blog/fast-csv-writing-for-r/>
    - <https://www.r-bloggers.com/fast-csv-writing-for-r/>
    - <https://blog.revolutionanalytics.com/2017/02/fst-fast-serialization-of-r-data-fames.html>
    - <https://edomt.github.io/File-IO-Storage/>
    - <http://www.fstpackage.org>

- bonne pratique pour les `data input/output`
    - <https://csgillespie.github.io/efficientR/efficient-inputoutput.html#top-5-tips-for-efficient-data-io>
    - <https://cloud.r-project.org/web/packages/rio/vignettes/rio.html>
    - <https://github.com/SciViews/data.io>

Suite à ces différentes lectures, je vous propose deux cas de figures.

## Premier cas de figures

Si le jeu de données est de taille importante et qu'il doit être compressé. Il doit également être rapidement écrit et lu, j'utilise le format `.fst` du package [`fst`](http://www.fstpackage.org). Ce format peut être lu avec R et avec Python. De plus l'utilisation de multi-threads rend ces fonctions très efficaces. Le système de compression est également très efficace.


```r
library(fst)
```

Vous pouvez voir qu'il détecte automatiquement le nombr de threads qu'il va pouvoir employer. 


```r
write_fst(x = "", path = "", compress = "")
```

La fonction requiert : 
- x : le jeu de données que l'on souhaite exporter
- path: le chemin d'accès où l'on souhaite exporter le jeu de données
- compress: une valeur allant de 0 à 100, avec 0 pour une compression nulle et 100 pour une compression maximale. 


```r
df <- read_fst(path = "")
```

La fonction requiert :
- path: le chemin d'accès du jeu de données

## Second cas

Si le jeu de données est de petite taille et qu'il doit être facilement accessible par de nombreux programmes, j'utilise le format `.csv`. Le package `readr` et le package `data.table` seront très efficaces dans ce cas. 

Attention, l'importation d'un csv avec data.table::fread() renvoit un data.table.

# Conclusion

Malgré mon envie, de réaliser de nombreux Benchmark, je viens de m'épargner une grand nombre d'heure de boulot pour réaliser un travail que de nombreuses personnes ont déjà réalisés. Je vais tout de même garder le dépot que j'ai créé pour répondre à cette question. L'évolution des fonctions est tellement rapide que je suis sur que les package `fst`sera dépassé par un autre rapidement. 

