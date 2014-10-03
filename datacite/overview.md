## Install packages 

If the below packages are not installed already, then load package


```r
# install.packages(c('plyr','alm','ggplot2','knitr'))
library("plyr")
library("knitr")
library("alm")
library("ggplot2")
```


## Read in data


```r
input.name <- "../data/datacite_dois_in_plos_articles_2014-09-10.csv"

# get list of plos DOIs with associated DataCite DOIs from CSV file
alm <- read.csv(input.name, stringsAsFactors = FALSE, header = TRUE, sep = ",")
```


Analyze where the DataCite DOIs come from using the DOI prefix

```r
datacenters <- count(alm, vars = "prefix")
kable(datacenters, format = "markdown")
```

|  prefix|  freq|
|-------:|-----:|
|   10.16|    29|
|   10.41|     1|
|   10.51|   346|
|   10.53|     1|
|   10.54|     5|
|   10.55|     2|



```r
knit("overview.Rmd")
```

```
## 
## 
## processing file: overview.Rmd
```

```
##   |                                                                         |                                                                 |   0%  |                                                                         |.......                                                          |  11%
##   ordinary text without R code
## 
##   |                                                                         |..............                                                   |  22%
## label: unnamed-chunk-5
##   |                                                                         |......................                                           |  33%
##   ordinary text without R code
## 
##   |                                                                         |.............................                                    |  44%
## label: unnamed-chunk-6
##   |                                                                         |....................................                             |  56%
##   ordinary text without R code
## 
##   |                                                                         |...........................................                      |  67%
## label: unnamed-chunk-7 (with options) 
## List of 1
##  $ results: chr "asis"
## 
##   |                                                                         |...................................................              |  78%
##   ordinary text without R code
## 
##   |                                                                         |..........................................................       |  89%
## label: unnamed-chunk-8
##   |                                                                         |.................................................................| 100%
##   ordinary text without R code
```

```
## output file: overview.md
```

```
## [1] "overview.md"
```



