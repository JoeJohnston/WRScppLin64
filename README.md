WRScpp
======


This package taken from [Mr. Xiao He](https://github.com/mrxiaohe/) who wrote a package which provides `C++` sub-routines for several iterative procedures in the `R` package `WRS` for robust statistics by [Dr. Rand Wilcox](http://dornsife.usc.edu/cf/labs/wilcox/wilcox-faculty-display.cfm). These `C++` sub-routines can provide substantial performance boosts. The raw code is in [here](https://github.com/mrxiaohe/robustmethods_cplusplus). 

Mac binariess are available [here](http://github.com/mrxiaohe/WRScpp).
Windows binaries are available [here](http://github.com/mrxiaohe/WRScppWIN).

###[Installation]
#### Install Development Packages
These are source files and you need development files to compile from source.
On Mint/Ubuntu, you can use 

      sudo apt-get install r-base-dev

to get these. See the [Rcpp FAQ](http://dirk.eddelbuettel.com/code/rcpp/Rcpp-FAQ.pdf) for more infomation.
Note that I have not tried to compile this on Mac or Windows. See above for those files.

Also, there are likely some dependencies I have already installed and are forgetting about. YMMV.

#### To install this package, four R packages are required:

* `WRS`
* `RcppArmadillo` and `Rcpp`: These two packages allow convenient interface between R and C++. `RcppArmadillo` requires `Rcpp`, so installing the first one will automatically prompt R to install the latter.
* `devtools`: This package allows R users to install packages hosted on Github.

        install.packages("WRS", repos="http://R-Forge.R-project.org", type="source")
        install.packages( c("RcppArmadillo", "devtools") )

####Next, load devtools and install WRScppLin from source:

    library("devtools")
    install_github(repo="JoeJohnston/WRScppLin")  


###[Some examples]

Load `WRScppLin`:

    library("WRScppLin")
    set.seed(1); dataset1 <- matrix(rnorm(1000), ncol=5)
    
    model.tsregC <- tsreg_C( x=dataset2[, 1:4], y=dataset2[, 5] )
    model.stsregC <- stsreg_C( x=dataset2[, 1:4], y=dataset2[, 5] )
    model.tshdregC <- tshdreg_C( x=dataset2[, 1:4], y=dataset2[, 5] )
    
    model.tsregC$coef
    model.stsregC$coef
    model.tshdregC$coef

    
