# Visualising Netflix Dataset

An interactive **Power BI dashboard** that explores Netflix movies and TV shows using IMDb data, covering release trends, ratings and audience voting from 1972 to 2022.

## Files
- `NetflixDashboard.pbix`: the Power BI dashboard (download and open in Power BI Desktop)
- `images/`: dashboard screenshots

## Questions Answered
1. Which were the most popular movies and TV shows over the last 50 years?
2. Is the dataset skewed toward recent release years?
3. How has the average IMDb score trended over time?
4. Have more people started voting on titles over the years?
5. How does age certification affect ratings (movies vs. TV shows)?

## Data Preparation (Power Query)
- Replaced `null` values in `age_certification` with `NA`
- Replaced `null` values in `imdb_votes` with the median, because the column has high outliers
- Created a custom column: `Rating Votes = imdb_score * imdb_votes`, so that popularity reflects both score and number of votes
- Loaded the cleaned dataset into the Power BI model

## Dashboard Features
- Slicers: **release_year** range (1972–2022) and **type** (Movie / Show)
- Column chart: most popular titles
- Line chart: number of titles per release year (skewness check)
- Combo chart: total IMDb votes (columns) and average IMDb score (line) by release year

## Screenshots

### Most Popular TV Shows
![Most Popular](images/most-popular.png)

### Dataset Skewness (Last 20 Years)
![Skewness](images/skewness.png)

### IMDb Votes & Score Trend: TV Shows
![Shows Trend](images/shows-trend.png)

### IMDb Votes & Score Trend: Movies
![Movies Trend](images/movies-trend.png)

## Key Insights

**Most popular TV shows**
- *Breaking Bad* leads by a wide margin (16.4M), followed by *Stranger Things* (8.6M), *The Walking Dead* (7.8M), *Black Mirror* (4.5M) and *House of Cards* (4.3M).

**Dataset skewness**
- The dataset is heavily skewed toward recent years. Titles per year stay below 50 until about 2014, then rise sharply to a peak of 286 in 2018.
- The drop in 2022 (92 titles) likely reflects incomplete data for that year rather than a real decline.

**IMDb score trends**
- *TV shows:* average scores were high (around 7.5–8.0) from the late 1990s through the 2000s and have drifted down to about 6.6 by 2022.
- *Movies:* average scores fluctuate between about 6 and 7 and also trend slightly downward, ending near 6.0 in 2022.

**Voting behaviour**
- Voting activity has grown a lot over time. Vote totals are near zero for older titles and peak after 2010.
- For TV shows, votes peak around 2017–2019 (3.21M in 2017). For movies, notable peaks are 6.2M in 2010 and about 6M in 2017–2019.
- Overall, more votes does not mean higher scores: the most-voted years tend to have lower average ratings.

## Tools Used
- Power BI Desktop
- Power Query
- DAX / custom columns

## How to Use
1. Download `NetflixDashboard.pbix`
2. Open it in Power BI Desktop
3. Use the year and type slicers to explore the data
