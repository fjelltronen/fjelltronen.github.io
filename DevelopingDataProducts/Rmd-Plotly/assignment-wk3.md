R Markdown Presentation and Plotly 
========================================================
author: fjelltronen
date: May 1st, 2018
autosize: true

(Use arrow keys to navigate between the slides)



Featured Date
========================================================


```r
Sys.Date()
```

```
[1] "2018-05-03"
```

Interactive Plot (Code)
========================================================

Using the `mtcars` dataset and `plotly`, `mpg` (*miles per gallon*; y-axis) is shown as a function of `hp` (*horse power*; x-axis), `cyl` (*number of cylinders*; color of markers), and `am` (*transmission*; 0 = automatic, 1 = manual; size of markers). The car models are used as the hovertext of each point.


```r
library(plotly)
data(mtcars) ## use the mtcars dataset
mtcars$cyl <- factor(mtcars$cyl)
## plot_ly to show mpg w.r.t hp, cyl, and am
p<-plot_ly(mtcars, x = ~hp, y = ~mpg, 
           alpha = 0.7, color = ~cyl, 
           size = ~am, type = "scatter", 
           mode = "markers", 
           hovertext = row.names(mtcars))
htmlwidgets::saveWidget(as.widget(p), file = "plotly.html")
```

Interactive Plot
========================================================
<iframe src="plotly.html" style="position:absolute;height:100%;width:100%"></iframe>
