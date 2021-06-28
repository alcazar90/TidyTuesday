## 2021-06-22: Public Park Access

----

**Lessons that I learned during this challenge:**

1. The `pdftools` used for [prepare the dataset](https://github.com/rfordatascience/tidytuesday/blob/master/data/2021/2021-06-22/readme.md) :wrench: and working with data in pdf files :open_mouth::

   ```R
   library(pdftools)
   pdftools::pdf_text(...pdf file...)
   ```

2. **Make annotations :writing_hand: outside the plot using a combination of `xlim` and `clip` argument inside `coord_cartesian`.**  Position the label in `max(year) + 1` then cut the x range with `xlim=c(min(year), max(year))` and used `clip="off"`that allow to plot outside the plot panel region.

   ```R
     ...
   	geom_text(aes(2021, p50, label=city),
               size = 3,
               data = pick((city %in% top5_near_cities)
                           & (year == 2020))) +
     coord_cartesian(xlim = c(2012, 2020),
                     clip = "off") +
   	...
   ```

3. **Use `stringr::str_wrap(text, width)` for align a text paragraph**.

   ```R
   text_17len <- "This is seventeen This is seventeen This is seventeen"
   cat(str_wrap(text_17len, width=17))
   ```

4. Reuse data within a `ggplot2` using filter in specific layer without creating a subset before. [It's possible create a function like `pick`](https://stackoverflow.com/questions/35806310/ggplot-plotting-layers-only-if-certain-criteria-are-met) to give logical conditions for filter the relevant data.

   ```R
   pick <- function(condition){   function(d) d %>% filter(!!enquo(condition)) }
   ```

   Now it's not necessary to create an entire `data.frame` with the `top_near_cities`:

   ```R
   ... +  
   geom_text(aes(2019.6, spr + 5, label=city),
               size = 3,
               family = "Oxygen",
               data = pick((city %in% top_near_cities)
                           & (year == 2020))) +
   ```

   ![./2021/2021-06-22_public_park/2021-06-22_publicPark.png](https://github.com/alcazar90/TidyTuesday/blob/main/2021/2021-06-22_public_park/2021-06-22_publicPark.png)

   





