# Findings: Cost of Living vs. Population in the World's Largest Cities

## Sample

- **100 cities** analyzed, drawn from a candidate pool of 250 large
  cities by population
- Numbeo had usable cost-of-living data for enough cities to fill the
  sample by reaching down to the **174th-largest** city in the world by
  population (out of 479 cities Numbeo tracks in total)
- Note: because the pool was widened to fill the 100-city target, this
  sample is best described as "the 100 largest cities with available
  Numbeo data," not a strict top-100-by-population ranking

## Population vs. cost of living: essentially no relationship

- Correlation coefficient: **r ≈ -0.09**
- City size does not meaningfully predict cost of living. Some of the
  cheapest cities measured are similar in population to some of the
  world's largest, most expensive metros.

## Top 10 best-value cities (highest purchasing power relative to cost)

| Rank | City | Country | Value Score |
|---|---|---|---|
| 1 | Hyderabad | India | 7.12 |
| 2 | Pune | India | 5.64 |
| 3 | Chennai | India | 5.35 |
| 4 | Bangalore | India | 5.32 |
| 5 | Jaipur | India | 3.97 |
| 6 | Nagpur | India | 3.97 |
| 7 | Kanpur | India | 3.97 |
| 8 | Chongqing | China | 3.94 |
| 9 | Chengdu | China | 3.88 |
| 10 | Indore | India | 3.76 |

7 of the top 10 are Indian cities; the remaining 3 are Chinese.

## Top 10 worst-value cities (lowest purchasing power relative to cost)

| Rank | City | Country | Value Score |
|---|---|---|---|
| 1 | Addis Ababa | Ethiopia | 0.27 |
| 2 | Abidjan | Côte d'Ivoire | 0.28 |
| 3 | Dar es Salaam | Tanzania | 0.87 |
| 4 | Alexandria | Egypt | 0.88 |
| 5 | Buenos Aires | Argentina | 0.93 |
| 6 | Giza | Egypt | 0.96 |
| 7 | New York City | United States | 1.00 |
| 8 | Cairo | Egypt | 1.01 |
| 9 | Tehran | Iran | 1.04 |
| 10 | Mexico City | Mexico | 1.06 |

Ranks 3–10 are close to a value score of 1.0 (costs and purchasing
power roughly balanced — not unusually bad, just average). Addis Ababa
and Abidjan are clear outliers, driven by very low local purchasing
power rather than high prices — their cost-of-living index is actually
moderate (42.6 and 45.2 respectively).

## Known limitations

- Numbeo's crowdsourced data skews toward wealthier, more-documented
  cities; several very large cities (particularly across Sub-Saharan
  Africa and South Asia) have thin or missing data
- Wikipedia's population figures come from varying reference years by
  city (recorded in the `population_year` column of the source data)
