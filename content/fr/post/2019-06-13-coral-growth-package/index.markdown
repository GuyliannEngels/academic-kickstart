---
title: "coral.growth : mon premier package" 
summary: "Réalisation de mon premier package"
author: [admin]
date: 2019-06-13 16:00:00
use_url: "https://econum.github.io/coral.growth/index.html"
categories: ["R", "BioDataScience"]
tags: ["R", "econum", "BioDataScience", "usethis", "thinkr", "pkgdown"]
---


```r
SciViews::R
```

```
## ── Attaching packages ───────────────────────────────────────────────── SciViews::R 1.1.0 ──
```

```
## ✔ SciViews  1.1.0        ✔ purrr     0.3.2   
## ✔ chart     1.3.0        ✔ readr     1.3.1   
## ✔ flow      1.0.0        ✔ tidyr     0.8.3   
## ✔ data.io   1.2.2        ✔ tibble    2.1.1   
## ✔ svMisc    1.1.0        ✔ ggplot2   3.1.1   
## ✔ forcats   0.4.0        ✔ tidyverse 1.2.1   
## ✔ stringr   1.4.0        ✔ lattice   0.20.38 
## ✔ dplyr     0.8.0.1      ✔ MASS      7.3.51.3
```

```
## ── Conflicts ────────────────────────────────────────────────────── tidyverse_conflicts() ──
## ✖ dplyr::filter() masks stats::filter()
## ✖ dplyr::lag()    masks stats::lag()
## ✖ dplyr::select() masks MASS::select()
```

# Introduction

Lors de la septième rencontres R qui s'est déroulé du 4 au 6 juillet 2018 à Rennes, j'ai au l'occasion de suivre une conférence sur [Fabriquer un package R en moins de 6 minutes la conférence ](https://r2018-rennes.sciencesconf.org/205552). 

Avant cette dernière, j'ai toujours pensé que l'écriture d'un package était limité au pro dans R. Après cette conférence, j'ai dédramatisé et j'ai voulu me lancer. Il ne me manquait plus qu'une idée intéressante pour en faire un package. 

J'ai décidé de réaliser un package sur la croissance des coraux scléractiniaires avec des fonctions très simples mais que les étudiants me demandent régulièrement.

- <https://econum.github.io/coral.growth/>

Pour m'aider dans cet exercice, j'ai employé les références suivantes :

- les conseils de thinkR: <https://thinkr.fr/creer-package-r-quelques-minutes/>
-  le package usethis qui fournit une aide préciseuse pour réalsier un packge : <https://usethis.r-lib.org>
- le package pkgdown pour documenter efficacement mon package <https://pkgdown.r-lib.org>
