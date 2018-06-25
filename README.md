# some_useful_R_functions
some useful R functions

### cleaning small values in regression tables
```
clean<-function(x)if(is.na(x)) " " else if(abs(x)<0.0001) "<=0.0001" else sprintf("%.4f",x)
clean<-Vectorize(clean)
```

### a function that generates all subsets
Ref: https://www.r-bloggers.com/generating-all-subsets-of-a-set/
```
library(plyr)
library(ggplot2)
all.subsets <- function(set) {
    n <- length(set)
    bin <- expand.grid(rlply(n, c(F, T)))
    mlply(bin, function(…) { set[c(…)] })
}
```
Example:
