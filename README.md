# Election Turnout Analysis in Polish Districts

## Project Overview

This project analyzes voter turnout in Polish districts (powiats) during the first round of the recent presidential elections, with a comparison to the turnout in the parliamentary elections of 2023. The analysis is focused on the rivalry between the two main political parties: **Civic Platform (PO)** and **Law and Justice (PiS)**.  

The main goals of the project are:
- To visualize voter turnout on a map of Poland at the district (powiat) level.
- To compare the results for PO and PiS between the two election events.
- To use Python tools and openly available data for transparent, reproducible analysis.

## Why this analysis?

- Historically, large cities in Poland tend to vote for PO, while rural areas and small towns lean towards PiS. This project investigates if this stereotype holds true in recent elections.
- Comparing the first round of the presidential election to the parliamentary election from 2023 is particularly interesting, because the turnout in the second round of presidential elections in Poland is usually higher, and 2023 had record turnout.
- By focusing on only two years apart, we reduce the impact of long-term social changes and make the comparison more meaningful.

## Data Sources

- **Polish district map in GeoJSON format**:  
  [GitHub repository with Polish district GeoJSON](https://github.com/ppatrzyk/polska-geojson/tree/master)
- **Election data**:  
  [Official Polish election results website](https://danewyborcze.kbw.gov.pl/indexc4fa.html?title=Strona_g%C5%82%C3%B3wna)

## Tools and Libraries

The analysis is performed in Python using the following libraries:
- **pandas** – for data wrangling and analysis
- **geopandas** – for geographic data handling and map visualization
- **matplotlib** – for plotting maps and charts

## How it works (Step-by-step):

1. **Download data**: Election results for Polish districts are downloaded from the official government website. The district boundaries (in GeoJSON format) are obtained from the linked GitHub repository.

2. **Prepare and clean the data**:
   - District codes (TERYT) are used to match election data with the map. Any format inconsistencies are fixed.
   - For each district, a flag is set indicating whether PO or PiS had a higher vote share.
   - Voter turnout is calculated as the percentage of issued ballots versus eligible voters.
   - Some data wrangling is necessary due to differences in column names or formats.

3. **Combine data with map**:
   - Election data is merged with the GeoJSON file using district names or codes.
   - Data is further cleaned to ensure compatibility (e.g., removing prefixes from district names).

4. **Visualization**:
   - Maps are created where each district is colored according to the winning party and the voter turnout.
   - Higher turnout makes the district color lighter; lower turnout makes it darker.
   - Each district displays the numerical turnout value directly on the map.

5. **Comparison**:
   - Results from the two election events are compared on separate maps for easier visual inspection.

## Example Map

*You will see a map of Poland, with each district colored by the winning party (orange for PO, blue for PiS), and the color's intensity reflects voter turnout.*
