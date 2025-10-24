# Sauti ya Mtaa: Analyzing 28 Years of Protest in Kenya (1997-Present)
## Overview

This project analyzes nearly three decades (1997-Present) of protest event data in Kenya using the Armed Conflict Location & Event Data Project (ACLED) dataset. The goal is to uncover trends, identify key drivers, understand the geographic distribution, and contextualize Kenyan protests within the East African region.

The analysis reveals a significant increase in protest activity over time, with major spikes historically driven by the five-year election cycle. However, recent years show a marked rise in protests driven by economic factors, particularly tax policies and the cost of living, suggesting a potential shift in the primary triggers for mass mobilization in Kenya.

This repository contains the Jupyter Notebook used for the analysis, the cleaned dataset, and generated visualizations.

## Data

* **Source:** [Armed Conflict Location & Event Data Project (ACLED)](https://acleddata.com/)
* **Raw Data File (Original):** `ACLED Data_2025-10-23.csv` (Contains data for all of Africa, multiple event types, approx. 30 columns).
* **Cleaned Data File (Used in Notebook):** `EA_data_clean.csv`
    * **Description:** This file contains only protest events (`event_type == 'Protests'`) for Kenya, Uganda, Tanzania, Ethiopia, and Somalia from 1997 onwards.
    * **Key Columns Kept:**
        * `event_id_cnty`: Unique event identifier.
        * `event_date`: Date of the protest event.
        * `year`: Year of the event.
        * `country`: Country where the event occurred.
        * `admin1`: County/First-level administrative region.
        * `sub_event_type`: Specific type of protest (e.g., Peaceful protest, Protest with intervention).
        * `fatalities`: Number of reported fatalities during the event.
        * `notes`: Text description of the event, crucial for identifying protest motives.

## Project Structure

## Setup and Installation

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/cabralchege/The-Rise-of-Protests-and-Public-Unrest.git](https://github.com/cabralchege/The-Rise-of-Protests-and-Public-Unrest)
    cd The-Rise-of-Protests-and-Public-Unrest
    ```

2.  **Create a Virtual Environment (Recommended):**
    ```bash
    python -m venv .venv
    source .venv\Scripts\activate  
    ```

3.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Data Acquisition:**
    * The cleaned dataset (`EA_data_clean.csv`) is included in the `data/` directory.

## Usage

1.  **Activate Virtual Environment:** `source .venv/bin/activate` (or equivalent).
2.  **Launch Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```
3.  **Open and Run:** Navigate to the `notebooks/` directory and open `Kenya_Protest_Analysis.ipynb`. Run the cells sequentially to perform the data cleaning (if needed), analysis, and generate visualizations. Saved graph images will appear in the `output/` directory.

## Analysis Overview

The `Protest_Data.ipynb` notebook performs the following steps:

1.  **Data Loading & Cleaning:** Loads the raw/cleaned data, converts dates, filters for relevant countries and event types, selects necessary columns.
2.  **Kenya Data Preparation:** Filters for Kenya-specific events and creates a `plot_category` ('Political', 'Economic', 'Other') based on keyword analysis of the `notes` column.
3.  **Time Series Analysis:**
    * Plots the trend of total annual protest events in Kenya (Graph 1).
    * Plots the trend of total annual fatalities during protests in Kenya (Graph 3).
4.  **Protest Driver Analysis:**
    * Groups protests by year and `plot_category`.
    * Generates a grouped bar chart showing the count of 'Political' vs. 'Economic' protests for key years (election years pre-2021, all years post-2021) (Graph 4).
5.  **Geographic Analysis:**
    * Identifies the top 10 counties in Kenya with the highest number of protests.
    * Generates a horizontal bar chart visualizing these hotspots (Graph 5).
6.  **Comparative Analysis:**
    * Compares the annual trend of protest events in Kenya against Uganda, Tanzania, Ethiopia, and Somalia (Graph 6).

## Visualizations

The primary visualizations generated (and saved to `output/`) are:

1.  **Graph 1:** Line chart showing the total number of protest events per year in Kenya (1997-Present).
2.  **Graph 3:** Line chart showing the total number of fatalities during protests per year in Kenya (1997-Present).
3.  **Graph 4:** Grouped bar chart comparing 'Political (Elections)' vs. 'Economic (Tax/Finance)' driven protests for selected years in Kenya.
4.  **Graph 5:** Horizontal bar chart showing the Top 10 Kenyan counties by total protest events.
5.  **Graph 6:** Multi-line chart comparing annual protest event counts for Kenya and selected East African peers.


## Key Findings

* There has been a significant **increase in the baseline level of protest activity** in Kenya over the past two decades.
* Historically, major **peaks in protest align strongly with the five-year general election cycle**.
* Since approximately 2021, **economic grievances** (related to taxes, cost of living, finance bills) have emerged as a dominant and sustained driver of protests, often surpassing election-related mobilization in non-election years.
* Protest activity is geographically concentrated, with **Nairobi** being the primary hotspot, followed by other major urban centers like Kisumu, Mombasa, and Nakuru.
* Periods of high protest intensity, particularly around contested elections (e.g., 2007-08, 2017), correlate with **significant spikes in reported fatalities**.
* Compared to its East African neighbors, Kenya exhibits a **more volatile and cyclical protest pattern**, likely influenced by its unique political dynamics and relatively more open civic space.

## Limitations & Future Work

* **Categorization:** The 'Political' vs. 'Economic' categorization relies on keyword matching in the `notes` field and may not capture the nuances of every event. Manual review or more advanced NLP could refine this.
* **Data Granularity:** While event-level data is used, deeper analysis could explore `sub_event_type` proportions (Peaceful vs. Violent) over time or correlate protest intensity (Fatalities/Event) with drivers.
* **Causality:** The analysis shows correlations (e.g., elections and protests), but establishing direct causality requires more rigorous methods.

**Future Ideas:**

* Incorporate economic indicators (inflation, unemployment) to correlate with economic protests.
* Analyze the role of specific actors mentioned in the `notes`.
* Compare protest *intensity* (Fatalities per Event) across counties or drivers.

## License
This project is licensed under the MIT License - see the `LICENSE` file for details (if you create one).

## Contact

Cabral Chege - cabralowiro@gmail.com
Project Live Link: [The-Rise-of-Protests-and-Public-Unrest](https://kenya-dissent-pulse.lovable.app/)
Article Link: [From pandas to 'Maandamano': A Data-Driven Story of Kenyan Protest](https://thecabralperspective.hashnode.dev/pandas-to-maandamano-kenya-protest-analysis)