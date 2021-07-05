## 2021-06-29: Animal Rescues

---

**Lessons that I learned during this challenge:**

1. Use `plot_layout()` for order the plot composition with `patchwork`:package:

   ```R
   viz <- map + line + plot_layout(nrow = 2, 
                                   ncol = 1, 
                                   height = c(2.5, 0.5))
   ```

   

2. The operator `p1|p2` for put `p2` behind `p1`. and for stacking the plots  `p1/p2` . In addition, if you want a stacked column and another full, you can compose with plot_layout to control the proportions of each plot in the stacking column, and then use the `|` to put bnehind the full column or the column with just one plot. 

   ```R
   viz <- map + line +  plot_layout(nrow=2, 
                                    ncol=1,
                                    height=c(2.5, .5))
   viz | vertical_bars 
   ```



![./2021/2021-06-29_animal_rescues/2021-06-29_animal_rescues.png](https://github.com/alcazar90/TidyTuesday/blob/main/2021/2021-06-29_animal_rescues/2021-06-29_animal_rescues.png)

