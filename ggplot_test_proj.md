ggplot_test_proj
================
Wilson
2022-08-29

## Setting up my environment

Notes: Setting up R environment by installing ‘tidyverse’ and the
‘palmerpenguins’ packages.

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.2 ──
    ## ✔ ggplot2 3.3.6     ✔ purrr   0.3.4
    ## ✔ tibble  3.1.8     ✔ dplyr   1.0.9
    ## ✔ tidyr   1.2.0     ✔ stringr 1.4.0
    ## ✔ readr   2.1.2     ✔ forcats 0.5.1
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
library(palmerpenguins)
```

### Loading the data

``` r
data(penguins)
```

## Visualizations

Here we will go through a series of Visualizations

### Body mass and flipper length

Here, we plot flipper length against body mass

``` r
ggplot(data = penguins) +
  geom_point(mapping = aes(x = flipper_length_mm, y = body_mass_g))
```

![](ggplot_test_proj_files/figure-gfm/ggplot%20for%20penguin%20data%20visualization-1.png)<!-- -->

### Flipper and Body mass by species

Here we plot flipper length against body mass, and filter it by species

``` r
ggplot(data = penguins) + 
  geom_point(mapping = aes(x = flipper_length_mm, y = body_mass_g,shape=species,color=species))
```

![](ggplot_test_proj_files/figure-gfm/species-1.png)<!-- -->

### Flipper and Body mass by species and sex

Here, we plot flipper against body mass and look at the breakdown by sex
and species

``` r
ggplot(data = penguins,mapping = aes(x = flipper_length_mm, y = body_mass_g)) +
  geom_point(aes(color=species,shape=species)) +
  facet_wrap(~sex)
```

![](ggplot_test_proj_files/figure-gfm/Sex-1.png)<!-- -->
