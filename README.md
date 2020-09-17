
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Building Tidy Tools

### Genentech 2020

by Charlotte Wickham and Sara Altman

## Important Links

[Sli.do](https://app.sli.do/event/71rqfi1i) for Q\&A and live polls

[Google
Doc](https://docs.google.com/document/d/1vahqtJ2d8zoidy1jZ19w3fxEBNWXY0YSarwtuoo-rkA/edit?usp=sharing)
for reporting on your breakout room progress

[Archive of
Q\&A](https://docs.google.com/document/d/1PxGsv9spATRa453Q2lboDmKA1BP0odC2vw5ipWLjqe8/edit?usp=sharing)
Questions and their answers from Slido

## Materials

Materials will be made available on
[github](https://github.com/cwickham/genentech-build-tidy-tools). The
materials will evolve as the workshop approaches, so if you want to
pre-download the materials, please wait until the day before the
workshop.

However, please don’t delay on [Setup](#setup). You’ll want to uncover
any problems in getting the required packages before our first session
together.

## Setup

<!-- Fix later to generate from content of repo like https://github.com/hadley/tidy-tools/blob/master/README.Rmd -->

The most important package for Day 1 is devtools:

``` r
install.packages("devtools")
```

If you’ve installed devtools before, you should check the component
packages are also up to date, by following any instructions under the
`devtools` section in the output of:

``` r
devtools::dev_sitrep()
```

To be prepared beyond Day 1, you’ll also need the following packages:

``` r
install.packages(c("glue", "hexbin", "skimr", "sloop", "tsibble", "usethis", "vctrs"))
```

``` r
# You may also need:
install.packages(c("ggplot2", "dplyr", "stringr"))

# And get some partial packages we'll work with later:
usethis::create_from_github("skaltman/fordogs", fork = FALSE)
usethis::create_from_github("cwickham/ns", fork = FALSE)
usethis::create_from_github("cwickham/tidytest", fork = FALSE)
```

<!-- 
* When you're done, put a green post-it on your computer. 
* If you need help, put up a pink post-it.
-->

If you’re all set, you might like to download the first set of slides.

## Schedule

<!--html_preserve-->

<table style="font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif; display: table; border-collapse: collapse; margin-left: auto; margin-right: auto; color: #333333; font-size: 16px; background-color: #FFFFFF; width: auto; border-top-style: solid; border-top-width: 2px; border-top-color: #A8A8A8; border-right-style: none; border-right-width: 2px; border-right-color: #D3D3D3; border-bottom-style: solid; border-bottom-width: 2px; border-bottom-color: #A8A8A8; border-left-style: none; border-left-width: 2px; border-left-color: #D3D3D3;">

<thead style="border-top-style: solid; border-top-width: 2px; border-top-color: #D3D3D3; border-bottom-style: solid; border-bottom-width: 2px; border-bottom-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3;">

<tr>

<th style="color: #333333; background-color: #FFFFFF; font-size: 100%; font-weight: normal; text-transform: inherit; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: bottom; padding-top: 5px; padding-bottom: 6px; padding-left: 5px; padding-right: 5px; overflow-x: hidden; text-align: left;" rowspan="1" colspan="1">

Day

</th>

<th style="color: #333333; background-color: #FFFFFF; font-size: 100%; font-weight: normal; text-transform: inherit; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: bottom; padding-top: 5px; padding-bottom: 6px; padding-left: 5px; padding-right: 5px; overflow-x: hidden; text-align: center;" rowspan="1" colspan="1">

8:30am-10:00am

</th>

<th style="color: #333333; background-color: #FFFFFF; font-size: 100%; font-weight: normal; text-transform: inherit; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: bottom; padding-top: 5px; padding-bottom: 6px; padding-left: 5px; padding-right: 5px; overflow-x: hidden; text-align: center;" rowspan="1" colspan="1">

10:30am-12:00pm

</th>

</tr>

</thead>

<tbody style="border-top-style: solid; border-top-width: 2px; border-top-color: #D3D3D3; border-bottom-style: solid; border-bottom-width: 2px; border-bottom-color: #D3D3D3;">

<tr>

<td style="padding-top: 8px; padding-bottom: 8px; padding-left: 5px; padding-right: 5px; margin: 10px; border-top-style: solid; border-top-width: 1px; border-top-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: middle; overflow-x: hidden; text-align: left;">

<div class="gt_from_md">

<p>

Mon Sep 14th

</p>

</div>

</td>

<td style="padding-top: 8px; padding-bottom: 8px; padding-left: 5px; padding-right: 5px; margin: 10px; border-top-style: solid; border-top-width: 1px; border-top-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: middle; overflow-x: hidden; text-align: center;">

<div class="gt_from_md">

<p>

<strong>Introduction / The Whole Game</strong>

</p>

<p>

<em>Charlotte</em>

</p>

<p>

<a href="https://github.com/cwickham/genentech-build-tidy-tools/raw/master/1-intro.pdf">Slides</a>

</p>

<p>

<small>Build a package from scratch before your first coffee
break.</small>

</p>

</div>

</td>

<td style="padding-top: 8px; padding-bottom: 8px; padding-left: 5px; padding-right: 5px; margin: 10px; border-top-style: solid; border-top-width: 1px; border-top-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: middle; overflow-x: hidden; text-align: center;">

<div class="gt_from_md">

<p>

<strong>Testing</strong>

</p>

<p>

<em>Sara</em>

</p>

<p>

<a href="https://github.com/cwickham/genentech-build-tidy-tools/raw/master/2-testing.pdf">Slides</a>

</p>

<p>

<small>Learn a testing workflow to give you confidence your code is
working as intended.</small>

</p>

</div>

</td>

</tr>

<tr>

<td style="padding-top: 8px; padding-bottom: 8px; padding-left: 5px; padding-right: 5px; margin: 10px; border-top-style: solid; border-top-width: 1px; border-top-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: middle; overflow-x: hidden; text-align: left;">

<div class="gt_from_md">

<p>

Tue Sep 15th

</p>

</div>

</td>

<td style="padding-top: 8px; padding-bottom: 8px; padding-left: 5px; padding-right: 5px; margin: 10px; border-top-style: solid; border-top-width: 1px; border-top-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: middle; overflow-x: hidden; text-align: center;">

<div class="gt_from_md">

<p>

<strong>Documentation / Sharing</strong>

</p>

<p>

<em>Sara</em>

</p>

<p>

<a href="https://github.com/cwickham/genentech-build-tidy-tools/raw/master/3-sharing.pdf">Slides</a>

</p>

<p>

<small>Learn how to add documentation to your package, as well as how to
share you package with the world.</small>

</p>

</div>

</td>

<td style="padding-top: 8px; padding-bottom: 8px; padding-left: 5px; padding-right: 5px; margin: 10px; border-top-style: solid; border-top-width: 1px; border-top-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: middle; overflow-x: hidden; text-align: center;">

<div class="gt_from_md">

<p>

<strong>Dependencies</strong>

</p>

<p>

<em>Charlotte</em>

</p>

<p>

<a href="notes/4-dependencies.Rmd">Notes</a>

</p>

<p>

<small>Learn how to use other packages in your own packages.</small>

</p>

</div>

</td>

</tr>

<tr>

<td style="padding-top: 8px; padding-bottom: 8px; padding-left: 5px; padding-right: 5px; margin: 10px; border-top-style: solid; border-top-width: 1px; border-top-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: middle; overflow-x: hidden; text-align: left;">

<div class="gt_from_md">

<p>

Wed Sep 16th

</p>

</div>

</td>

<td style="padding-top: 8px; padding-bottom: 8px; padding-left: 5px; padding-right: 5px; margin: 10px; border-top-style: solid; border-top-width: 1px; border-top-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: middle; overflow-x: hidden; text-align: center;">

<div class="gt_from_md">

<p>

<strong>Using the tidyverse in packages</strong>

</p>

<p>

<em>Charlotte</em>

</p>

<p>

<a href="notes/5-tidyverse.Rmd">Notes</a>

</p>

<p>

<small>Explore the challenges of including tidyverse packages in your
own packages.</small>

</p>

</div>

</td>

<td style="padding-top: 8px; padding-bottom: 8px; padding-left: 5px; padding-right: 5px; margin: 10px; border-top-style: solid; border-top-width: 1px; border-top-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: middle; overflow-x: hidden; text-align: center;">

<div class="gt_from_md">

<p>

<strong>Interface</strong>

</p>

<p>

<em>Sara</em>

</p>

<p>

<a href="notes/6-interface.Rmd">Notes</a>

</p>

<p>

<small>Learn how decisions about the name and arguments of your
functions influence how easy they are to learn and use.</small>

</p>

</div>

</td>

</tr>

<tr>

<td style="padding-top: 8px; padding-bottom: 8px; padding-left: 5px; padding-right: 5px; margin: 10px; border-top-style: solid; border-top-width: 1px; border-top-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: middle; overflow-x: hidden; text-align: left;">

<div class="gt_from_md">

<p>

Thu Sep 17th

</p>

</div>

</td>

<td style="padding-top: 8px; padding-bottom: 8px; padding-left: 5px; padding-right: 5px; margin: 10px; border-top-style: solid; border-top-width: 1px; border-top-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: middle; overflow-x: hidden; text-align: center;">

<div class="gt_from_md">

<p>

<strong>Interface II</strong>

</p>

<p>

<em>Charlotte</em>

</p>

<p>

<a href="notes/7-interface-ii.Rmd">Notes</a>

</p>

<p>

<small>Learn how decisions about the output of your functions influence
how easy they are to learn and use.</small>

</p>

</div>

</td>

<td style="padding-top: 8px; padding-bottom: 8px; padding-left: 5px; padding-right: 5px; margin: 10px; border-top-style: solid; border-top-width: 1px; border-top-color: #D3D3D3; border-left-style: none; border-left-width: 1px; border-left-color: #D3D3D3; border-right-style: none; border-right-width: 1px; border-right-color: #D3D3D3; vertical-align: middle; overflow-x: hidden; text-align: center;">

<div class="gt_from_md">

<p>

<strong>OO programming / S3</strong>

</p>

<p>

<em>Charlotte</em>

</p>

<p>

<a href="notes/8-oop.Rmd">Notes</a>

</p>

<p>

<small>Learn how S3 objects work, and can improve the interface of your
package.</small>

</p>

</div>

</td>

</tr>

</tbody>

</table>

<!--/html_preserve-->

The notes will be live coded and committed as we go, so they may be
empty if you are looking at them before the workshop.

You can see the scripts we’ll work from in [`script/`](script/), but we
recommend not reading too far ahead because you’ll find answers to some
of the exercises, and you’ll learn more if you try to work through them
first.

## Getting Help

[**Sli.do**](https://app.sli.do/event/71rqfi1i): Ask a question in the
Q\&A at anytime. Also vote on other peoples’ questions.

**In Breakout Rooms:**

  - Ask your roommates
  - If your room is stuck, “Ask for help” in the [Google
    Doc](https://docs.google.com/document/d/1vahqtJ2d8zoidy1jZ19w3fxEBNWXY0YSarwtuoo-rkA/edit?usp=sharing)

**Zoom chat:** Reserved for urgent technical matters (e.g. “we can’t
hear you”)

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
            dplyr](https://dplyr.tidyverse.org/articles/programming.html)
          - [Using ggplot2 in
            packages](https://ggplot2.tidyverse.org/articles/ggplot2-in-packages.html)
          - Only if you want/need the theory: [Metaprogramming in
            Advanced R](https://adv-r.hadley.nz/metaprogramming.html)
    
      - Object Oriented Programming / S3: [Object Oriented Programming
        in Advanced R](https://adv-r.hadley.nz/oo.html)

  - General R programming:
    
      - [Advanced R](https://adv-r.hadley.nz/), in particular the
        Foundations part
      - [Programming notes from Data Challenge
        Lab](https://dcl-prog.stanford.edu/)

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

-----

These materials closely follow <https://github.com/hadley/tidy-tools>

![](https://i.creativecommons.org/l/by/4.0/88x31.png) This work is
licensed under a [Creative Commons Attribution 4.0 International
License](https://creativecommons.org/licenses/by/4.0/).
