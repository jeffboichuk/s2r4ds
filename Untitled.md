Live code from purrr session at rstudio::conf
================
Jenny Bryan
2018-02-05

Where to find this document
---------------------------

Shortlink humans can type:

-   <http://bit.ly/jenny-live-code>

Horrible link that reveals how this is done:

-   <https://www.dropbox.com/s/2b8mi4rir23pvnx/jenny-live-code.R?raw=1>

Using the `raw=1` query trick for rendering a DropBox-hosted file in the browser:

-   <https://www.dropbox.com/en/help/desktop-web/force-download> learned from [Michael Levy](https://twitter.com/ucdlevy).

How this works:

-   I code live in an R script locally. I save often.
-   This file lives in a directory synced to DropBox.
-   You open the DropBox file at <http://bit.ly/jenny-live-code> and refresh as needed.
-   Should allow you to see, copy, paste everything I've typed and save the entire transcript at the end. This file is highly perishable, so save your own copy if you want it.
-   Every now and then the refresh won't work. Just re-open from from the bit.ly link: <http://bit.ly/jenny-live-code>

Workshop material starts here
-----------------------------

``` r
library(tidyverse) ## includes purrr, which is our main attraction today
## ── Attaching packages ────────────────────────────────────── tidyverse 1.2.1 ──
## ✔ ggplot2 2.2.1     ✔ purrr   0.2.4
## ✔ tibble  1.4.2     ✔ dplyr   0.7.4
## ✔ tidyr   0.7.2     ✔ stringr 1.2.0
## ✔ readr   1.1.1     ✔ forcats 0.2.0
## ── Conflicts ───────────────────────────────────────── tidyverse_conflicts() ──
## ✖ dplyr::filter() masks stats::filter()
## ✖ dplyr::lag()    masks stats::lag()
library(repurrrsive)

## Completely frivolous playing around with different idioms
## for iteration
## Will wake everyone up and focus on ITERATION!

## https://github.com/brooke-watson/BRRR
## devtools::install_github("brooke-watson/BRRR")
library(BRRR)

skrrrahh(2)
skrrrahh(35)
skrrrahh("bigsean5")

for(i in 1:5) {
  Sys.sleep(0.75)
  skrrrahh(i)
}

walk(1:5, ~{Sys.sleep(0.75); BRRR::skrrrahh(.x)})

f <- function(sound, sleep = 0.75) {
  Sys.sleep(sleep)
  skrrrahh(sound)
}
```
