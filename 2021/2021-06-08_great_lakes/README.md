## 2021-06-08: :fish: Great Lakes Fish :tropical_fish:

**Lessons that I learned during this challenge:**

1. Enrich text in titles using `ggtext` 📦 (Further informatioin [here](https://github.com/wilkelab/ggtext)).
1. Create a function to display labels and then used it with `geom_text()`.
1. From [David Robinson screencast](https://www.youtube.com/watch?v=1Zj_JJYIk5o) using `fct_lump()` to keep the `n` top categories and aggregate the others (i.e. "Others"). It is helpful to compress information and focus on the most critical categories...but in the end, I decided to show all fish species.
    ```
    # Keep the top 5 categories and compress the others.
    mutate(
          aggregate_species = fct_lump(species, 5, w = values)
          )
    ```
1. The plot is trying to show a lot of information. A better solution is to just visualise the production % distribution. 


![./2021/2021-06-08_great_lakes/great_lake_production.png](https://github.com/alcazar90/TidyTuesday/blob/main/2021/2021-06-08_great_lakes/great_lake_production.png)



