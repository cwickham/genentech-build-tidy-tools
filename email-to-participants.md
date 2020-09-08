We are excited to meet you all next week in "Building Tidy Tools"!

The most important link to have at hand is:
https://github.com/cwickham/genentech-build-tidy-tools  
 (shortlink: [bit.ly/build-tt](http://bit.ly/build-tt)).

This is where you'll find the materials 
and other important information.  

In particular, the course will be hands-on, 
so before Monday, 
please make sure you have the R packages described in the [Setup section of the README](https://github.com/cwickham/genentech-build-tidy-tools#setup), 
which is pasted below for your reference.

You might also like to check out the [Schedule](https://github.com/cwickham/genentech-build-tidy-tools#schedule)
for our four mornings together.
We'll meet 8:30am to 12:00pm each day, 
with a 30 minute break from 10:00am to 10:30am.

We'll get you the Zoom link once it is finalized.

If you have any questions feel free to email Charlotte,
cwickham@gmail.com, directly.

See you next week,  
Charlotte and Sara

## Setup

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
install.packages(c("glue", "hexbin", "sloop", "usethis", "vctrs"))
```

``` r
# You may also need:
install.packages(c("ggplot2", "dplyr", "stringr"))

# And get the package we'll work with later:
usethis::create_from_github("skaltman/fordogs", fork = FALSE)
```