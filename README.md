# Cost of Living vs. Population: 100 Largest World Cities

A web-scraping project (built with R's `rvest`) comparing cost of living
across the world's largest cities, to test whether population size
predicts affordability and to identify the best- and worst-value large
cities by purchasing power.

## What this does

1. Scrapes a list of the world's largest cities by population from
   Wikipedia (`List of cities with over one million inhabitants`).
2. Scrapes Numbeo's cost-of-living rankings table (cost of living index,
   rent index, groceries index, restaurant index, local purchasing power
   index) for hundreds of cities in a single page load.
3. Matches the two datasets by city name (exact match, then fuzzy
   matching via `stringdist` for naming differences), widening the pool
   of candidate cities as needed until 100 cities with valid cost-of-
   living data are found.
4. Computes a **value score** (local purchasing power ÷ cost of living
   index) for each matched city — a rough proxy for how far a typical
   local salary stretches against local prices.
5. Produces three plots: population vs. cost of living, top 10
   best-value cities, and top 10 worst-value cities.

## Files

- `scrape_cost_of_living.R` — the full scraping and analysis script
- `largest_cities_population.csv` — raw scraped population data
- `numbeo_col_rankings.csv` — raw scraped Numbeo rankings
- `cities_col_merged.csv` — final matched dataset used for analysis

## Requirements

```r
install.packages(c("rvest", "dplyr", "stringr", "purrr", "readr",
                    "tidyr", "stringdist", "ggplot2", "scales"))
```

## How to run

Open `scrape_cost_of_living.R` in R or RStudio and run it top to bottom.
It makes two web requests total (one to Wikipedia, one to Numbeo), so it
runs in seconds. The script prints diagnostic messages along the way —
how many cities matched, how far down the population ranking it had to
reach to fill the sample (`N_TARGET = 100`), and which cities in that
range still have no Numbeo match.

## Key findings

- **No relationship between population and cost of living** (r ≈ -0.09)
  — city size does not predict affordability.
- **Best-value large cities** are dominated by Indian metros (Hyderabad,
  Pune, Chennai, Bangalore) and two Chinese cities (Chongqing, Chengdu),
  where local purchasing power is high relative to living costs.
- **Worst-value large cities** split into two groups: cities where cost
  and purchasing power are simply balanced near the New York baseline
  (Mexico City, Cairo, Buenos Aires), and a distinct outlier group
  (Abidjan, Addis Ababa) where costs are moderate but local purchasing
  power is very low.

## Known limitations

- Numbeo's data is crowdsourced and skews toward wealthier,
  more-documented cities — several very large cities (particularly in
  Sub-Saharan Africa and South Asia) have thin or missing data.
- Because the candidate pool was widened to reach 100 matched cities,
  the final sample is best described as *"the 100 largest cities with
  available Numbeo data"* rather than a strict top-100-by-population
  comparison (it reaches down to the 174th-largest city).
- Wikipedia's population figures are not all from the same reference
  year; each row's `population_year` column records the year used.
