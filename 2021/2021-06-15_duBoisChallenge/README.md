## 2021-06-15: DuBoisChallenge 

**Lessons that I learned during this challenge:**


1. Maybe this could de obvious but was an aha-moment: 
    ```
    geom_segment + coord_polar = geom_curve
    ```
1. Using `geom_point` to highlight popular tweets while recycling `geom_step` axis.
Also, use the y-axis just to create a gap between the two layers.
1. Combine different plots into a single visualisation using `patchwork` 📦 (Further information [here](https://patchwork.data-imaginist.com/index.html)).
    ```
    (base_plot + top_wordCloud)  +
      plot_layout(heights = c(1, .45))  
    ```
1. Move the legends to a different position and also change the
legend title above w.r.t. the mapping, for example.
   ```
    theme(
      legend.position = "bottom" 
    ) + 
    guides(
      colour = guide_colorbar(title.position = "top",
                              title.hjust = 0.5),
    )
    ```

Questions:

1. 

![./2021/2021-06-15_duBoisChallenge/2021-06-15_duBoisChallenge.png](https://github.com/alcazar90/TidyTuesday/blob/main/2021/2021-06-15_duBoisChallenge/2021-06-15_duBoisChallenge.png)


