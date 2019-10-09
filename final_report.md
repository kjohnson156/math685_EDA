---
title: "EDA project"
author: "Math 685 students"
date: "9/20/2019"
output: 
  html_document: 
    keep_md: yes
keep_md: yes
---








Is there a relationship between the year the house was sold and the sale price?

First, let's look at the distribution of the year the house was sold. 


```r
summary(ames_clean$Yr.Sold)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##    2006    2007    2008    2008    2009    2010
```


```r
ggplot(data = ames_clean, mapping = aes(x = Yr.Sold)) +
  geom_histogram(binwidth = 0.1)
```

![](final_report_files/figure-html/unnamed-chunk-2-1.png)<!-- -->


Looking between 2006 and 2010, it looks like more houses were sold in 2007 (n=694) and the least amount of houses were sold in 2010 (n=341). 


Now to look at sale price. 


```r
summary(ames_clean$SalePrice)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   12789  129500  160000  180796  213500  755000
```



```r
ggplot(data = ames_clean, mapping = aes(x = SalePrice)) +
  geom_histogram(binwidth = 100000)
```

![](final_report_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

The lowest sale price was $12,789 and the highest was $755,000. The average sale price was $180,796.



```r
ggplot(ames_clean, aes(x=SalePrice, fill=Yr.Sold)) + 
    geom_histogram() + 
    facet_wrap(~Yr.Sold)+
  geom_freqpoly(binwidth = 10000)+
  coord_cartesian(xlim = c(0, 550000))
```

```
## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.
```

![](final_report_files/figure-html/unnamed-chunk-5-1.png)<!-- -->

When looking at year sold and sales price......

(I feel that this might make more sense if I broke these out by year?)
