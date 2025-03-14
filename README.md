# Azure / Databricks Formula 1 Project

## Objective
Develop and manage a Data Pipeline using Databricks and Azure to analyze and visualize Formula 1 race results.

### Overview
For a comprehensive introduction to Formula 1 racing, visit this https://f1chronicle.com/a-beginners-guide-to-formula-1/

![F1 Overview](./images/overview.png)

## Data Source
The dataset for all Formula 1 races from the 1950s onwards is obtained from an open-source API called Ergast Developer API ((http://ergast.com/mrd/)). The API provides the following tables:
 - Races: Information about each race, including date, location, and circuit details.
 - Drivers: Details about drivers, such as their name, nationality, and career statistics.
 - Constructors: Information about the teams, including their names and nationalities.
 - Results: Race results, including positions, points, and times.
 - Lap Times: Detailed lap times for each driver in every race.
 - Pit Stops: Information on pit stops made by drivers during races.
 - Qualifying: Results of the qualifying sessions, including positions and times.
 - Seasons: Information about each season, including year and championship standings.
 - Circuits: Details about the circuits, including name, location, and length.
 - With these tables, you can build a comprehensive data pipeline to analyze and visualize Formula 1 race results over the decades.

![Data Model](https://ergast.com/images/ergast_db.png)

Attributes of each tables is described in http://ergast.com/docs/f1db_user_guide.txt. Each tables is present as a single line/multiline CSV or JSON file in the data folder. 




## Structure
- 1.ingestion - Contains notebooks to ingest all data files from the raw layer to the ingested layer. Handles the incremental data for files: results, pitstops, laptimes, and qualifying.
2.trans - Contains notebooks to transform the data from the ingested layer to the presentation layer. Performs transformations to set up for analysis.
3.set-up - Notebooks to mount ADLS storages (raw, ingested, presentation) in Databricks.
4.includes - Contains notebooks with helper functions used in transformations.
5.analysis - Contains SQL files for finding the dominant drivers and teams. Prepares results for visualization.
6.raw - Contains SQL files to create ingested tables using Spark SQL.
7.utils - Contains SQL files to drop all databases for incremental load.
8.data - Contains sample raw data from the Ergast API.

## Technologies Used:
- Datadricks
- Azure
- ADF
- PySpark
- Python


