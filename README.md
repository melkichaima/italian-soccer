# italian-soccer
---
title: "Which is the best team ever in Italian soccer?"
output: html_document
editor_options:
  chunk_output_type: inline
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(cache = FALSE, echo = TRUE, eval = FALSE, message = FALSE, warning = FALSE, fig.align = 'center')
```

This challenge explores all matches of Italian soccer Serie A league from 1993 to current year. The dataset is contained in the website [football-data.co.uk](http://www.football-data.co.uk/italym.php).

### Challenges

1. Think about how to scrape the data from the website, but write no code at this stage.
1. Ask AI to write code to import data by scraping the website. Select only columns Date, HomeTeam, AwayTeam, FTHG (home team goals), FTAG (away team goals) and filter rows with a valid (not NA) Date.
1. Using dplyr and tidyr packages (no for loops!), compute statistics for every team (matches, wins, loses, draws, points, points per match). Hint: mutate a column with the outcome of the match (for instance, H = home teams wins, A = away team wins, P = draw). Then group by team and outcome (home and away) and hence spread the outcome. Do this step without the use of AI.
1. Come up with at least 3 data questions on the data at hand. Just write the questions, do not find the answers.

---

## Challenge 1 — Scraping approach (no code)

The data lives at [football-data.co.uk/italym.php](http://www.football-data.co.uk/italym.php), where each season (1993/94 onward) has a link to a CSV file named with a pattern like `mmz4281/<season code>/I1.csv` (e.g. `9394` for 1993/94, `2425` for 2024/25).

To get all seasons, I would scrape the page's HTML to extract every link ending in `I1.csv`, then download and read each CSV, combining them into one dataframe.


## Challenge 4 — Data questions (no answers)

1. Has the average number of goals scored per match changed over time, and are there any periods with particularly high or low scoring?
2. Which teams benefit the most from playing at home, and does the size of the home advantage differ across seasons?
3. Which teams are the most consistent from season to season, and which teams show the greatest variation in their performance over time?
