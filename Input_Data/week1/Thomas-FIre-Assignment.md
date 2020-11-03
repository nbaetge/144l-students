Thomas Fire Assignment
================
Kerri Luttrell
10/19/2020

## Load Data

``` r
fire.data <- read_excel("~/Github/144l_students/Input_Data/week1/Thomas_Fire_Progression.xlsx")
```

## Plot Data

``` r
p <- ggplot(fire.data, aes(x=Date))+ 
  geom_point(aes(y= PM10, colour = "PM10"))+
  geom_point(aes(y= Containment*1.5, colour = "Containment"))+
  scale_y_continuous(sec.axis = sec_axis(~./1.5, name = "Containment Level"))+
  scale_colour_manual(values = c("blue", "red"))+
  labs(y = "PM10 Abundance",
                x = "Date",
                colour = "Parameter", title = "PM10 Abundance and Containment Level over Time")+
  theme(legend.position = c(0.8, 0.6))
p
```

    ## Warning: Removed 1 rows containing missing values (geom_point).

![](Thomas-FIre-Assignment_files/figure-gfm/plot%20data-1.png)<!-- -->

## Analysis

This data shows the relationship of containment levels and PM10
abundance over time. From this graph we can observe that PM10 abundance
increased to nearly 150 the first few days of data collection. As the
Thomas Fire became more contained, the PM10 levels eventually decreased
and stayed at or below fifty. The oscillations below fifty could be due
to this being a more ambient range subject to normal environmental
dynamics rather than representative of particulate matter due to fire.
This is important because it shows pretty rapid decline of PM10
abundance in response to fire containment, with no long lag times. This
could inform recommendations on the duration of N95 face mask use.