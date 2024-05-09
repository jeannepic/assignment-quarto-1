# assignment-quarto-1
---
title: "Assignment Jeanne Pic"
format: html
editor: 
  markdown: 
    wrap: 72
---

## Quarto

Quarto enables you to weave together content and executable code into a
finished document. To learn more about Quarto see <https://quarto.org>.

## Running Code

When you click the **Render** button a document will be generated that
includes both content and the output of embedded code. You can embed
code like this:

```{r}
1 + 1
```

You can add options to executable code like this

```{r}
#| echo: false
2 * 2
```

The `echo: false` option disables the printing of code (only output is
displayed).

```{r} 
unicef_indicator_2 <- read.csv("/cloud/project/unicef_indicator_2.csv", sep=";")

# Install packages
install.packages("maps")
install.packages("ggplot2")

# Load packages
library(ggplot2)
library(maps)
library(dplyr)  

# Load the HIV data
data <- read.csv("unicef_indicator_2")

# World map visualization
ggplot() +
  geom_map(data = map_data("world"),
           map = map_data("world"),
           aes(x = long, y = lat, map_id = region),
  labs(title = "World Map")
ind_2007 <- gapminder %>% 
  filter(year == 2010)
map_world <- map_data("world") 
map_2010 <- full_join(map_world, ind_2007, by = c("region" = "country"))
ggplot(data = map_2010) +
  aes(x = long, y = lat, group = group,) +
  geom_polygon()

# Histogram visualization
ggplot(data) +
  geom_histogram(aes(x = unicef_indicator_2)) +
  labs(title = "Histogram of Observed Value of HIV Females Recving Antiretroviral treatments against child transmission", x = "Observed Value", y = "Frequency")

# Scatter plot visualization
ggplot(data, aes(x = year(2010), y = unicef_indicator_2, color = uni_indi_3)) +
  geom_point() +
  labs(title = "Scatter Plot: HIV Females per Year", x = "Year", y = "HIV Females")

# Time series plot
ggplot(data, aes(x =year(2010) , y = unicef_indicator_2, color = uni_indi_3)) +
  geom_line() +
  labs(title = "Time Series Plot: HIV Females receiving antiretroviral treatments against child transmission Over the Years", x = "Year", y = "Number")
