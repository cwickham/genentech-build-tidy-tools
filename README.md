
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Building Tidy Tools

### Genentech 2020

by Charlotte Wickham and Sara Altman

## Setup

<!-- Fix later to generate from content of repo like https://github.com/hadley/tidy-tools/blob/master/README.Rmd -->

Please make sure you’ve installed the following packages:

``` r
install.packages("devtools")
install.packages(c("fs", "glue", "hexbin", "lobstr", "rematch2", "sloop", "vctrs"))
devtools::install_github("r-lib/itdepends")
```

``` r
# You may also need:
install.packages(c("ggplot2", "dplyr", "stringr"))

# And get the package we'll work with later:
usethis::create_from_github("hadley/fordogs", fork = FALSE)

# if you see an error about "unsupported protocol", try this:
usethis::create_from_github("hadley/fordogs", fork = FALSE, protocol = "https")
```

<!-- 
* When you're done, put a green post-it on your computer. 
* If you need help, put up a pink post-it.
-->

If you’re all set, you might like to download the first set of slides.

## Slides

  - [Introduction and “The Whole Game”](1-intro.pdf)
  - [Unit Tests](2-testing.pdf)
  - [Documentation and Sharing](3-sharing.pdf)

## Code

Find our live coded notes in [`notes/`](notes/) as we commit them.

You can see the scripts we’ll work from in [`script/`](script/), but we
recommend not reading too far ahead because you’ll find answers to some
of the exercises, and you’ll learn more if you try to work through them
first.

## Where to learn more

  - **Workflow, devtools and usethis:**
    
      - [R Packages, 2nd Ed.](https://r-pkgs.org/), *work in progress*
    
      - [R Packages, 1st Ed.](http://r-pkgs.had.co.nz/)
    
      - [What they forgot to teach you about R](https://rstats.wtf/)

  - **Interface:** [Tidyverse design
    guide](https://design.tidyverse.org/), *work in progress*

  - **Implementation:**
    
      - Tidy evaluation:
        
          - [Programming with
            dplyr](https://dplyr.tidyverse.org/dev/articles/programming.html)
          - [Using ggplot2 in
            packages](https://ggplot2.tidyverse.org/dev/articles/ggplot2-in-packages.html)
          - Only if you want/need the theory: [Metaprogramming in
            Advanced R](https://adv-r.hadley.nz/metaprogramming.html)
    
      - Object Oriented Programming / S3: [Object Oriented Programming
        in Advanced R](https://adv-r.hadley.nz/oo.html)

## Overview

This is a hands on workshop for those who have embraced the tidyverse
and now want to expand it to meet their own needs. We’ll discuss API
design, functional programming tools, the basics of object design in S3,
and the tidy eval system for NSE.

At the end of the workshop participants will be able to:

  - Apply an efficient workflow for building R packages, documenting
    functions and unit testing using the usethis and devtools packages.

  - Implement commonly used frameworks inside packages like tidy
    evaluation and object oriented programming.

  - Critique the interface of a package and suggest improvements that
    would make the package easier to learn and use.

You should take this workshop if you have experience programming in R
and want to learn how to tackle larger scale problems. You’ll get the
most from it if you’re already familiar with functions and are
comfortable with R’s basic data structures (vectors, matrices, arrays,
lists, and data frames).

## Is this course for me?

Have you written a few of your own R functions? Are you ready to start
sharing your code (or data) through R packages? Are you curious what you
can do to make your first R packages easy for your users to use, and for
you to maintain?

## Materials

Materials will be made available on
[github](https://github.com/cwickham/genentech-build-tidy-tools). The
materials will evolve as the workshop approaches, so if you want to
pre-download the materials, please wait until the day before the
workshop.

## Schedule

## Day 1: Sep 14th

Introduction / The Whole Game **Charlotte**  
Testing **Sara**

## Day 2: Sep 15th

Documentation / Sharing **Sara**  
Dependencies **Charlotte**

## Day 3: Sep 16th

Using the tidyverse in packages **Charlotte**  
Interface **Sara**

## Day 4: Sep 17th

Interface II **Charlotte**  
OO programming / S3 **Charlotte**

-----

These materials closely follow <https://github.com/hadley/tidy-tools>

![](https://i.creativecommons.org/l/by/4.0/88x31.png) This work is
licensed under a [Creative Commons Attribution 4.0 International
License](https://creativecommons.org/licenses/by/4.0/).
