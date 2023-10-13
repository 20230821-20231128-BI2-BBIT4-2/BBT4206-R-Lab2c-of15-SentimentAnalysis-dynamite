Business Intelligence Lab Submission Markdown
================
<Dynamite>
\<13th October 2023\>

- [Student Details](#student-details)
- [Setup Chunk](#setup-chunk)
- [Loading a dataset](#loading-a-dataset)
  - [](#section)
  - [Different Sentiments that were performed in the
    data](#different-sentiments-that-were-performed-in-the-data)

# Student Details

<table>
<colgroup>
<col style="width: 53%" />
<col style="width: 46%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Student ID Numbers and Names of Group Members</strong></td>
<td><ol type="1">
<li><p>136017 - C - Unika Mureithi</p></li>
<li><p>135864 - C - Winnie Githua</p></li>
<li><p>120313 - C - Daniel Obala</p></li>
<li><p>136804 - C - Joy Mutai</p></li>
<li><p>133598 - C - Shirlene Ouma</p></li>
</ol></td>
</tr>
<tr class="even">
<td><strong>GitHub Classroom Group Name</strong></td>
<td>Dynamite</td>
</tr>
<tr class="odd">
<td><strong>Course Code</strong></td>
<td>BBT4206</td>
</tr>
<tr class="even">
<td><strong>Course Name</strong></td>
<td>Business Intelligence II</td>
</tr>
<tr class="odd">
<td><strong>Program</strong></td>
<td>Bachelor of Business Information Technology</td>
</tr>
<tr class="even">
<td><strong>Semester Duration</strong></td>
<td>21<sup>st</sup> August 2023 to 28<sup>th</sup> November 2023</td>
</tr>
</tbody>
</table>

# Setup Chunk

**Note:** the following “*KnitR*” options have been set as the
defaults:  
`knitr::opts_chunk$set(echo = TRUE, warning = FALSE, eval = TRUE, collapse = FALSE, tidy.opts = list(width.cutoff = 80), tidy = TRUE)`.

More KnitR options are documented here
<https://bookdown.org/yihui/rmarkdown-cookbook/chunk-options.html> and
here <https://yihui.org/knitr/options/>.

**Note:** the following “*R Markdown*” options have been set as the
defaults:

> output:  
>   
> github_document:  
> toc: yes  
> toc_depth: 4  
> fig_width: 6  
> fig_height: 4  
> df_print: default  
>   
> editor_options:  
> chunk_output_type: console

# Loading a dataset

Describe the code chunk here: Here the dataset is being loaded from the
root folder

``` r
# Fill this with R related code that will be executed when the R markdown file
# is rendered using knitR
library(readr)
# STEP 3. Load the Dataset ---- student_performance_dataset <-
# read_csv('data/20230412-20230719-BI1-BBIT4-1-StudentPerformanceDataset
# copy.CSV',)
```

Describe the next code chunk here: Here the overall sentiments are
applied after the relationship between the likes/wishes are put into
place

``` r
# Fill this with other R related code that will be executed when the R markdown
# file is rendered using knitR
library(readr)
# Inner Join the Likes/Wishes with the Corresponding Sentiment(s) ----
# evaluation_likes_filtered_nrc <- evaluation_likes_filtered %>%
# inner_join(get_sentiments('nrc'), by = join_by(`Likes (tokenized)` == word),
# relationship = 'many-to-many')

## evaluation_wishes_filtered_nrc <- evaluation_wishes_filtered %>%
## inner_join(get_sentiments('nrc'), by = join_by(`Wishes (tokenized)` ==
## word), relationship = 'many-to-many')


# Fill this with other R related code that will be executed when the R markdown
# file is rendered using knitR
library(readr)
# Overall Sentiment ---- Evaluation Likes ---- nrc_likes_plot <-
# evaluation_likes_filtered_nrc %>% group_by(sentiment) %>% You can filter by
# the class group if you wish filter(`Class Group` == 'A') %>%
# summarise(word_count = n()) %>% ungroup() %>% mutate(sentiment =
# reorder(sentiment, word_count)) %>% `fill = -word_count` is used to make the
# larger bars darker ggplot(aes(sentiment, word_count, fill = -word_count)) +
# geom_col() + guides(fill = FALSE) + # Turn off the legend blue_grey_theme() +
# labs(x = 'Sentiment', y = 'Word Count') + scale_y_continuous(limits = c(0,
# 15000)) + #Hard code the axis limit ggtitle('Lexicon-Based Sentiment Analysis
# of Course Evaluation Likes') + coord_flip()
```

## 

``` r
# Fill this with other R related code that will be executed when the R markdown
# file is rendered using knitR
library(readr)
```

## Different Sentiments that were performed in the data

Describe the code chunk here: Here the Frequency sentiment is being
performed

``` r
# Fill this with R related code that will be executed when the R markdown file
# is rendered using knitR
library(readr)
# Frequency Sentiment per Group and per Gender ---- nrc_likes_chord <-
# evaluation_likes_filtered_nrc %>% filter(decade != 'NA' & !sentiment %in%
# c('positive', 'negative')) %>% count(sentiment, `Class Group`) %>%
# group_by(`Class Group`, sentiment) %>% summarise(sentiment_sum = sum(n)) %>%
# filter(sentiment_sum > 10) %>% mutate(sentiment = reorder(sentiment,
# sentiment_sum)) %>% ungroup()
```

**etc.** as per the lab submission requirements.
