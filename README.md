
<!-- README.md is generated from README.Rmd. Please edit that file -->

# Building Tidy Tools

### Genentech 2020

by Charlotte Wickham and Sara Altman

## Materials

Materials will be made available on
[github](https://github.com/cwickham/genentech-build-tidy-tools). The
materials will evolve as the workshop approaches, so if you want to
pre-download the materials, please wait until the day before the
workshop.

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
usethis::create_from_github("hadley/fordogs", fork = FALSE, 
  protocol = "https")
```

<!-- 
* When you're done, put a green post-it on your computer. 
* If you need help, put up a pink post-it.
-->

If you’re all set, you might like to download the first set of slides.

## Schedule

<!--html_preserve-->

<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#nbpfdvtvih .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#nbpfdvtvih .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#nbpfdvtvih .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#nbpfdvtvih .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 4px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#nbpfdvtvih .gt_bottom_border {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#nbpfdvtvih .gt_col_headings {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#nbpfdvtvih .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#nbpfdvtvih .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#nbpfdvtvih .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#nbpfdvtvih .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#nbpfdvtvih .gt_column_spanner {
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#nbpfdvtvih .gt_group_heading {
  padding: 8px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#nbpfdvtvih .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#nbpfdvtvih .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#nbpfdvtvih .gt_from_md > :first-child {
  margin-top: 0;
}

#nbpfdvtvih .gt_from_md > :last-child {
  margin-bottom: 0;
}

#nbpfdvtvih .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: solid;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#nbpfdvtvih .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: solid;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 12px;
}

#nbpfdvtvih .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#nbpfdvtvih .gt_first_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
}

#nbpfdvtvih .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#nbpfdvtvih .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: double;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#nbpfdvtvih .gt_table_body {
  border-top-style: solid;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: solid;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#nbpfdvtvih .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#nbpfdvtvih .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding: 4px;
}

#nbpfdvtvih .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#nbpfdvtvih .gt_sourcenote {
  font-size: 90%;
  padding: 4px;
}

#nbpfdvtvih .gt_left {
  text-align: left;
}

#nbpfdvtvih .gt_center {
  text-align: center;
}

#nbpfdvtvih .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#nbpfdvtvih .gt_font_normal {
  font-weight: normal;
}

#nbpfdvtvih .gt_font_bold {
  font-weight: bold;
}

#nbpfdvtvih .gt_font_italic {
  font-style: italic;
}

#nbpfdvtvih .gt_super {
  font-size: 65%;
}

#nbpfdvtvih .gt_footnote_marks {
  font-style: italic;
  font-size: 65%;
}
</style>

<div id="nbpfdvtvih" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">

<table class="gt_table">

<thead class="gt_col_headings">

<tr>

<th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1">

Day

</th>

<th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1">

8:30am-10:00am

</th>

<th class="gt_col_heading gt_columns_bottom_border gt_center" rowspan="1" colspan="1">

10:30am-12:00pm

</th>

</tr>

</thead>

<tbody class="gt_table_body">

<tr>

<td class="gt_row gt_left">

<div class="gt_from_md">

<p>

Mon Sep 14th

</p>

</div>

</td>

<td class="gt_row gt_center">

<div class="gt_from_md">

<p>

<strong>Introduction / The Whole Game</strong>

</p>

<p>

<em>Charlotte</em>

</p>

<p>

<a href="1-intro.pdf">Slides</a>

</p>

</div>

</td>

<td class="gt_row gt_center">

<div class="gt_from_md">

<p>

<strong>Testing</strong>

</p>

<p>

<em>Sara</em>

</p>

<p>

<a href="2-testing.pdf">Slides</a>

</p>

</div>

</td>

</tr>

<tr>

<td class="gt_row gt_left">

<div class="gt_from_md">

<p>

Tue Sep 15th

</p>

</div>

</td>

<td class="gt_row gt_center">

<div class="gt_from_md">

<p>

<strong>Documentation / Sharing</strong>

</p>

<p>

<em>Sara</em>

</p>

<p>

<a href="3-sharing.pdf">Slides</a>

</p>

</div>

</td>

<td class="gt_row gt_center">

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

</div>

</td>

</tr>

<tr>

<td class="gt_row gt_left">

<div class="gt_from_md">

<p>

Wed Sep 16th

</p>

</div>

</td>

<td class="gt_row gt_center">

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

</div>

</td>

<td class="gt_row gt_center">

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

</div>

</td>

</tr>

<tr>

<td class="gt_row gt_left">

<div class="gt_from_md">

<p>

Thu Sep 17th

</p>

</div>

</td>

<td class="gt_row gt_center">

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

</div>

</td>

<td class="gt_row gt_center">

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

</div>

</td>

</tr>

</tbody>

</table>

</div>

<!--/html_preserve-->

The notes will be live coded and committed as we go, so they may be
empty if you are looking at them before the workshop.

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

-----

These materials closely follow <https://github.com/hadley/tidy-tools>

![](https://i.creativecommons.org/l/by/4.0/88x31.png) This work is
licensed under a [Creative Commons Attribution 4.0 International
License](https://creativecommons.org/licenses/by/4.0/).
