## 2021-07-27: Olympic Medals

----

**Lessons that I learned during this challenge:**

1. **Use `sysfonts::font_add_google(name = "font_name"` for download and used fonts for google fonts**.

   ```R
   sysfonts::font_add_google(name = "Tiitillium Web")
   showtext::showtext_auto()
   
   theme_set(theme_minimal(base_family = "Titillium Web",
                          base_size = 16))
   ```

2. **Use the `stroke` argument to control the line width when using `geom_point.**

3. **Add an image to the plot with `patchwork::inset_element`**. The left, bottom, right and top arguments must be used considering they can "stretch" or "squish" the image.

   ```r
   img <- png::readPNG("olympic-rings.png", TRUE)
   (p + patchwork::inset_element(img,
                                left = 0.06,
                                bottom = 0.05,
                                right = 0.90,
                                top = 0.20,
                                clip = FALSE))
   ```

![./2021/2021-07-27_olympic_medals/2021-07-27_olympic_timeline.png](https://github.com/alcazar90/TidyTuesday/blob/main/2021/2021-07-27_olympic_medals/2021-07-27_olympic_timeline.png)

