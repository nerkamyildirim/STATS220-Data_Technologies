# Joey's got an assignment!

```{r}
library(magick)

# square one
text1 <- image_blank(width = 500,
            height = 100,
            color = "#ffffff") %>%
  image_annotate(text = "The assignment \nis due in 2 weeks",
                 color = "#000000",
                 size = 40,
                 font = "Helvetica",
                 gravity = "center")

# square two
joey_happy <- image_read("https://www.meme-arsenal.com/memes/c9f636ca17c692708575e8e1bbc3025f.jpg") %>%
              image_trim() %>% image_scale(500)

# square three 
text2 <- image_blank(width = 500,
                     height = 100,
                     color = "#ffffff") %>%
  image_annotate(text = "The assignment \nis due in 2 days",
                 color = "#000000",
                 size = 40,
                 font = "Helvetica",
                 gravity = "center")

# square four
joey_shocked <- image_read("https://www.meme-arsenal.com/memes/701622228dffb51ac07525916c903654.jpg") %>%
                image_scale(500)

# square five
text3 <- image_blank(width = 500,
                     height = 100,
                     color = "#ffffff") %>%
  image_annotate(text = "The assignment \nis due in 2 hours",
                 color = "#000000",
                 size = 40,
                 font = "Helvetica",
                 gravity = "center")

# square six
joey_dead <- image_read("https://www.meme-arsenal.com/memes/701622228dffb51ac07525916c903654.jpg") %>%
   image_negate() %>% image_scale(500)

# creating vectors and rows
happy_vector <- c(text1, joey_happy) %>% image_append()
shocked_vector <- c(text2, joey_shocked) %>% image_append()
dead_vector <- c(text3, joey_dead) %>% image_append()

meme <- c(happy_vector, shocked_vector, dead_vector) %>% 
      image_append(stack = TRUE) %>% image_write("my_meme.png")
      
```
