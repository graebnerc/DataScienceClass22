---
title: Using exercises
author: Claudius Gräbner-Radkowitsch
date: '2022-03-01'
slug: using-exercises
categories:
  - setup
  - tutorial
  - exercises
tags:
  - introduction
output: 
  html_document:
    theme: readable
    highlight: tango
    toc: true
    toc_depth: 2
    number_sections: true
---



When learning a programming language, applying the new concepts regularly
is absolutely essential. Without regular practice it is hard to impossible
to remember everything you need to actually enjoy working with R.

Therefore, I prepared a small set of exercises for each session that I 
recommend you to do after the session. This will help you to remember what 
you have learned and to find out what you did not understand well. I then urge
you to post your problems on Moodle, to ask your colleagues and to help each
other out. This also will be a great boost to your learning progress: 
explaining something to others is not only great in a normative sense, it also
helps you to get a deeper understanding of the concepts yourself.

In this short post I quickly explain how you can use the exercises that I have
prepared for you. For those of you interested in the underlying mechanics:
all exercises were prepared using the package 
[learnr](https://rstudio.github.io/learnr/) together with
the [gradethis](https://github.com/rstudio/gradethis) package, 
and are distributed in the package `DataScienceExercises`.

To use the exercises you must have installed the packages `learnr`, `gradethis`
and `DataScienceExercises`. If you followed the instructions in the tutorial on 
[installing R packages](/post/installing-packages/) this should be the case. 
If for some reasons you need to install them, you can do this via:


```r
pack_names <- c(
  "rstudio/learnr",
  "rstudio/gradethis",
  "graebnerc/DataScienceExercises"
)
remotes::install_github(
  repo = pack_names, upgrade = "always")
```

Note that this requires a previous installation of the package `remotes`:


```r
install.packages("remotes")
```

Since I update the exercises according to your feedback, and add new 
exercises over the semester, I strongly recommend you to update the package
`DataScienceExercises` each time before you start practicing.
To do so you need an internet 
connection. If you just want to *do* the exercises without updating the 
package, an internet connection is *not* required: the exercises themselves
also work offline.

To update the package, simply type the following into the console and press
`Enter`:


```r
remotes::install_github(
  repo = "graebnerc/DataScienceExercises", upgrade = "always")
```

This should update your package version to the most recent release.

If you want to start an exercise you first need to figure out the name of the
exercise sheet. This is provided in the Material section of the course 
webpage. Then you call execute the following code via the console in R Studio,
replacing 'EX_NAME' with the name of the exercise sheet:


```r
learnr::run_tutorial(
  name = "EX_NAME", 
  package = "DataScienceExercises", 
  shiny_args=list("launch.browser"=TRUE))
```

The first exercise sheet, for instance, is called `Basics`. Thus, to call it
execute the following:


```r
learnr::run_tutorial(
  name = "Basics", 
  package = "DataScienceExercises", 
  shiny_args=list("launch.browser"=TRUE))
```

Lastly, if you encounter a bug or a mistake, or have an idea for a good 
exercise, please let me know via the 
[issue tracker](https://github.com/graebnerc/DataScienceExercises/issues)
of the `DataScienceExercises` package or via Moodle. Thank you!