# ggplotJrnold

Some extra themes and scales for [ggplot](http://had.co.nz/ggplot2/),

- The Economist theme and scales
- [Solarized](http://ethanschoonover.com/solarized) theme and scales
- Themes and scales based on Stata graph schemes
- Theme and scales based on the classic ugly Excel 2003 charts (for fun only)
- Shape scales from William S. Cleveland's *Elements of Graphing Data*
- Minimal-ink Tufte theme and a new geom, **geom_range_frame**.

# Install 

It is probably easiest to use the **devtools** package to install the latest version:




```r
library(devtools)
install_github('ggplotJrnold', 'jrnold')
```

# Examples


```r
library(ggplot2)
library(ggplotJrnold)
dsamp <- diamonds[sample(nrow(diamonds), 1000), ]
```


## Tufte theme and geom_range_frame


```r
(ggplot(mtcars, aes(wt, mpg)) + geom_point() + geom_range_frame() + 
    theme_tufte())
```

![plot of chunk unnamed-chunk-3](http://i.imgur.com/0TFzJ.png) 


## Economist theme

A theme that approximates the style of plots in The Economist
magazine.


```r
(qplot(carat, price, data = dsamp, colour = cut) + theme_economist() + 
    scale_colour_economist())
```

![plot of chunk unnamed-chunk-4](http://i.imgur.com/96TlB.png) 


## Solarized theme

A theme and color and fill scales based on the Solarized palette.

A light theme with blue accents.


```r
(qplot(carat, price, data = dsamp, colour = cut) + theme_solarized() + 
    scale_colour_solarized("blue"))
```

![plot of chunk unnamed-chunk-5](http://i.imgur.com/SVePV.png) 


A dark theme with red accents.


```r
(qplot(carat, price, data = dsamp, colour = cut) + theme_solarized(light = FALSE) + 
    scale_colour_solarized("red"))
```

![plot of chunk unnamed-chunk-6](http://i.imgur.com/o2sYp.png) 


## Stata theme 

A theme and color/fill scales based on the graphs in Stata.


```r
(qplot(carat, price, data = dsamp, colour = cut) + theme_stata() + 
    scale_colour_stata() + ggtitle("Plot Title"))
```

![plot of chunk unnamed-chunk-7](http://i.imgur.com/uOlia.png) 


## Excel 2003 theme

For that classic ugly look and feel. For ironic purposes only. 3D bars
and pies not included.


```r
(qplot(carat, price, data = dsamp, colour = cut) + theme_excel2003() + 
    scale_colour_excel2003())
```

![plot of chunk unnamed-chunk-8](http://i.imgur.com/l3Dq8.png) 



```r
(ggplot(diamonds, aes(clarity, fill = cut)) + geom_bar() + scale_fill_excel2003(fill = TRUE) + 
    theme_excel2003())
```

![plot of chunk unnamed-chunk-9](http://i.imgur.com/ET7r4.png) 


Please never use this theme.
