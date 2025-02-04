widget to widget interaction with R Shiny
========================================================
author: Elliot Hohn
date: May 13, 2021
autosize: true

Inspiration
========================================================

At The Freshwater Trust we build a lot of dashboards and
visualization tools where interaction would be realluy useful.
![](img/sps.png)


Many ways to interface with JS libraries in R
========================================================

![](img/plotly_book.png)
***

Many great R wrappers for JS libraries, such as {plotly}, {r2d3}, {mapboxapi}, {reactable}, {leaflet}, {DT}, etc.


```r
library(plotly)

p <- plot_ly(alpha = 0.5) %>%
  add_histogram(x = ~rnorm(500)) %>%
  add_histogram(x = ~rnorm(500) + 1) %>%
  layout(barmode = "overlay")

htmlwidgets::saveWidget(as.widget(p), file = "demo.html")
```

Easy interactivity
========================================================
<iframe src="demo.html" style="position:absolute;height:200%;width:200%"></iframe>

Demo
========================================================
- Use {crosstalk} with {plotly} and {reactable} to link brushing and filtering between table and plot
- Use {htmlwidgets} to add a custom javascript function
that allows table and map interaction

Example 1 - 
========================================================
