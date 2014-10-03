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

# DOI prefixes are not numbers
datacenters$prefix <- as.factor(datacenters$prefix)

# generate markdown table
kable(datacenters, format = "markdown")
```

|prefix   |  freq|
|:--------|-----:|
|10.1594  |    29|
|10.4123  |     1|
|10.5061  |   346|
|10.5281  |     1|
|10.5441  |     5|
|10.5524  |     2|



```r
knit("overview.Rmd", quiet = TRUE)
```

```
## [1] "overview.md"
```



