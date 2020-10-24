Developing Data Product W3Assignment
========================================================
author: Zixin Zhang
date: 24/10/2020
autosize: true

First Slide
========================================================

This presentation include a short analysis of dataset *iris*, a 3D surface plot. And the result is presented by **Plotly** Package.


Generating figures
========================================================

```r
# data iris 
data(iris)
fig <- iris %>% 
    plot_ly() %>%
    add_trace(x = ~Sepal.Length, y = ~Sepal.Width, type = 'scatter',
              color = ~ Species) %>%
    layout(title = "sepal width and length of different species",
           xaxis = list(title = 'Sepal Length'),
           yaxis = list(title = 'Sepal Width'))

# 3D surface 
x <- seq(-10,10,0.1)
y <- seq(-10,10,0.1)
X <- replicate(length(y), x)
Y <- t(replicate(length(x), y))
coef <- dnorm(sqrt(X^2 + Y^2), mean = 0, sd = 5)

Z <- sin((X^2+Y^2)/10)*coef
surf <- plot_ly(x = X, y = Y, z = Z, type = 'surface') %>%
    layout(title = "A 3D surface")
```

Slide With Plot 1
========================================================
## Analysis of the iris data




```
Error in file(con, "rb") : cannot open the connection
```
