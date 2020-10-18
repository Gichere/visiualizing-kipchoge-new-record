# Visualizing Eliud Kipchoge INEOS new marathon record in Viena, Austria
On saturday October 12, 2019, Eliud Kipchoge broke (unofficially) the two-hour marathon barrier.
I saw Neil Saunders’ Twitter post on visualizing the new record and decided to try and reproduce it with runners instead of points. 
I obtained the data from a Wikipedia page with {rvest}R package, wrangled and tidied it and eventually plotted it using {ggimage} R package.
## I hope this short project can show how R is a powerful yet interesting and versatile language in the field of data science


```{r, warning=FALSE}
library(tidyverse)
library(rvest)
library(janitor)
library(lubridate)
library(ggimage)
library(hrbrthemes)
```
We’ll use {tidyverse} for tidy manipulation and plotting, {janitor} for cleaning the column names, {lubridate} for working with dates, {ggimage} for a plot with images and {hrbrthemes} for a nice quick aesthetic theme.

## Retrieving data from wikipedia
In order to view the new record in comparison to other world records, We’ll turn to Wikipedia and see what we can find there. We only want the table with men’s records, so let’s get that:


