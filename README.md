# Film Data Analysis for Microsoft
## Flatiron School Data Science Phase 1 Project

**Student Name**: [Rafael V Rabinovich](mailto:rafvrab@gmail.com)<br>
**Student Pace**: Flex pace<br>
**Instructors**: Morgan Jones, Mark Barbour<br>
**Blog URL**: https://medium.com/@rafvrab

## Business Understanding
Analyzing datasets for Microsoft's film venture to provide actionable insights. Tasked with understanding key factors for successful box office performance. The primary stakeholders are Microsoft's Board of Directors, guiding decisions on genres, directors, and critical success factors. The project empowers the Board to curate a high-potential movie portfolio.

## Data Overview
Utilizing datasets from Box Office Mojo, IMDb, Rotten Tomatoes, The Movie DB, and The Numbers for comprehensive analysis.
- **Box Office Mojo**: `bom.movie_gross.csv.gz` (53,544 bytes)
- **IMDb**: `im.db.zip` (67,149,708 bytes)
  - Key Tables: `df_mb`, `df_dir`, `df_kf`, `df_akas`, `df_ratings`, `df_persons`, `df_principals`, `df_writers`
- **Rotten Tomatoes**: `rt.movie_info.tsv.gz` (498,202 bytes), `rt.reviews.tsv.gz` (3,402,194 bytes)
- **The Movie DB**: `tmdb.movies.csv.gz` (827,840 bytes)
- **The Numbers**: `tn.movie_budgets.csv.gz` (153,218 bytes)
- 
**Student Name**: [Rafael V Rabinovich](mailto:rafvrab@gmail.com)<br>
**Student Pace**: Flex pace<br>
**Instructors**: Morgan Jones, Mark Barbour<br>
**Blog URL**: https://medium.com/@rafvrab

# Business Understanding
Analyzing datasets for Microsoft's film venture to provide actionable insights. Tasked with understanding key factors for successful box office performance. The primary stakeholders are Microsoft's Board of Directors, guiding decisions on genres, directors, and critical success factors. The project empowers the Board to curate a high-potential movie portfolio.

# Data Understanding
### Data Sources Overview
The project utilizes the following data files:
- **Box Office Mojo**: `bom.movie_gross.csv.gz` (53,544 bytes)
- **IMDb**: `im.db.zip` (67,149,708 bytes)
  - Key Tables: `df_mb`, `df_dir`, `df_kf`, `df_akas`, `df_ratings`, `df_persons`, `df_principals`, `df_writers`
- **Rotten Tomatoes**: `rt.movie_info.tsv.gz` (498,202 bytes), `rt.reviews.tsv.gz` (3,402,194 bytes)
- **The Movie DB**: `tmdb.movies.csv.gz` (827,840 bytes)
- **The Numbers**: `tn.movie_budgets.csv.gz` (153,218 bytes)
- 
# Data Preparation
#### Data Exploration Process
This section outlines the steps involved in preparing and cleaning the dataset for analysis. The dataset consists of various movie-related tables obtained from different sources.

#### Retrieval and Unzipping

The provided notebook includes instructions and code to retrieve the raw data and unzip the files containing movie-related information from various sources. Multiple datasets were acquired, such as Box Office Mojo, Rotten Tomatoes movie info and reviews, The Movie DB, and The Numbers, among others.

#### Exploring SQL Database Tables

Utilizing SQL database files, the notebook connected to the IMDb database to retrieve and explore its tables. Detailed information regarding the database tables' contents and their corresponding Pandas DataFrames is provided.

#### Statistical Analysis

Various statistical analyses were performed on different DataFrames derived from the dataset, showcasing descriptive statistics for attributes such as movie ratings, runtime, and other relevant movie-related data.

#### Data Shape and Structure

The README presents tabular forms displaying the shape and structure of each table, including the number of rows and columns they contain. Detailed descriptions of column titles and their respective tables are also provided for clarity.

#### Frame Mergers

The process of merging different DataFrames to combine relevant information into a single consolidated DataFrame is described step-by-step. This merging process aimed to link directors, actors, movie titles, genres, ratings, and other critical information into a unified dataset for analysis.

#### Data Cleaning

Following the merging process, steps were taken to clean the dataset, including the removal of duplicates and unnecessary columns. The cleaned dataset focuses on retaining essential information required for analysis while eliminating redundant or irrelevant data points.

### Merger of Other Data Frames

The following code snippets demonstrate the process of merging different DataFrames and performing relevant data cleaning steps:

#### Merging 'movie_basics' with 'movie_ratings'

The code snippet shows how the DataFrames 'df_mb' and 'df_ratings' are merged using the `pd.merge()` function on the 'movie_id' column with a "left" merger.

#### Checking for Duplicates and Cleanliness

The code checks for duplicates in the resulting merged DataFrame 'df_im_mgd'. It also verifies if there are any null values present in the dataset.

#### DataFrame Shape and Display

The code snippet provides insights into the shape of the DataFrame 'df_im_mgd' and displays the first few rows of the merged DataFrame to visualize the data.

#### Merging 'df_mg', 'db_movies', and 'db_movie_budgets'

Demonstrates the merging process of 'df_mg', 'db_movies', and 'db_movie_budgets' DataFrames. It explains the merging methodology and drops unnecessary columns from the resulting DataFrame 'unified_df'.

#### Final Merging Process

Displays the final merging process by merging 'unified_df' with 'db_movie_budgets' based on specified columns. It drops redundant columns and displays the resulting 'final_df' DataFrame.

#### Additional Merging with 'filtered_merged_df'

Describes the additional merging process with 'filtered_merged_df' based on the 'primary_title' and 'title' columns, displaying the 'merged_final_df' DataFrame.

### Data Preparation for `merged_final_df`

The data preparation phase involved cleaning the dataset and organizing it for analysis. Columns were converted to numeric values by removing commas and dollar signs from the 'worldwide_gross' and 'production_budget' columns. Additionally, the desired column order was defined to structure the dataset for further analysis.

# Exploratory Data Analysis

Calculating ROI, visualizing top genres, analyzing metrics, categorizing production budgets, and exploring seasonal and staff influences.

#### Return on Investment (ROI) Calculation

The ROI and net profit for each movie were computed using the provided formulas: Net Profit = Gross Revenue - Budget, and ROI = (Net Profit / Budget) * 100. These metrics were calculated to gauge the profitability of movies in the dataset.
### Data Visualizations
#### Top 25 Film Genres by ROI
Bar plot showcasing top 25 film genres by mean ROI.

#### Various Metrics Analysis
Multiple bar plots analyzing profit, ROI, rating, votes, and runtime.

### Production Budget Analysis and Categorization
Dataset categorized by lower, middle, and higher budget segments. Bar plot visualizes median production budgets.

### Genre Analysis
Identifies top 3 genres with best ROI in each budget category.

### Seasonal Analysis
Grouped films by month and year, calculating average ROI. Line plot shows ROI fluctuations.

### Staff Analysis
Explores impact of staff roles on ROI. Visualizes average ROI per profession, identifying top 10 roles and top 3 individuals in each budget category.


## Recommendations
Tailored suggestions for lower, middle, and higher budget films, including genres, seasonal trends, and staff recommendations.

### Lower Budget Recommendations
- **Genres**: Comedy, Romance, Sport
- **Seasons**: February, August, May
- **Staff**: Levan Gabriadze (Director, Actor, Camera Department), Jamie Buckner (Miscellaneous, Production Manager, Producer), Tom Boyle (Producer, Writer, Cinematographer)

![Lower Budget Recommendations](Images/lbr.jpg)

### Middle Budget Recommendations
- **Genres**: Horror, Mystery, Thriller
- **Seasons**: July, November, January
- **Staff**: Sam Taylor-Johnson (Director, Producer, Actress), Seth MacFarlane (Writer, Music Department, Producer), Conrad Vernon (Actor, Producer, Animation Department)

![Middle Budget Recommendations](Images/mbr.jpg)

### Higher Budget Recommendations
- **Genres**: Biography, Drama, Music
- **Seasons**: April, June, July
- **Staff**: Kyle Balda (Director, Animation Department, Visual Effects), Chris Buck (Animation Department, Director, Writer), Jennifer Lee, Jared Bush (Writer, Miscellaneous, Producer)

![Higher Budget Recommendations](Images/hbr.jpg)

### Overall Recommendations
Overall, the lower budget bracket (below $15 million per film) consistently yields the best ROI. Genre and staff significantly influence ROI, surpassing the impact of the release season.
![Overall Recommendations](Images/oar.jpg)


## Conclusions
Optimizing film production across budgets, with an emphasis on the lower bracket for superior ROI.

## Limitations
Analysis limited to provided dataset, potential data limitations, and high-level overview.

## Next Steps
Deeper exploration of film markets, acquiring recent data, and revisiting original datasets for enhanced completeness.

# Structure Map
GitHub Repository: https://github.com/rafvrab/MovieAnalysis/tree/main
┌ .gitignore<br>
├ Film_Analysis.pdf<br>
├ README.md<br>
└ analysis.ipynb<br><br>
Data Files Repository: https://github.com/learn-co-curriculum/dsc-phase-1-project-v2-4/tree/master/zippedData
┌ bom.movie_gross.csv.gz<br>
├ im.db.zip<br>
├ rt.movie_info.tsv.gz<br>
├ rt.reviews.tsv.gz<br>
├ tmdb.movies.csv.gz<br>
└ tn.movie_budgets.csv.gz<br>
