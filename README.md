
# India General Election 2024 - Results Analysis

This repository contains a comprehensive analysis of the 2024 Indian General Election results. The project provides in-depth insights into voter behavior, constituency-specific outcomes, and state-level performance indicators through a dynamic and interactive dashboard.

## Table of Contents
- [Project Objective](#project-objective)
- [Dataset Description](#dataset-description)
- [Methodology](#methodology)
- [Dashboard Snapshots](#dashboard-snapshots)
- [Enhanced Entity-Relation (EER) Diagram](#enhanced-entity-relation-eer-diagram)
- [SQL Analysis](#sql-analysis)

## Project Objective
The primary goal of this project is to analyze the results of the India General Election 2024. By leveraging data from multiple sources, we aim to provide a clear and detailed understanding of the electoral outcomes at various levels – from individual constituencies to national alliances.

## Dataset Description

The analysis is based on four key CSV files:

*   **`constituencywise_results.csv`**: This file contains the primary results for each constituency, including details about the winning and trailing candidates.
    *   `Constituency`, `Const. No.`, `Parliament Constituency Name_Number`: Identifiers for each electoral constituency.
    *   `Leading Candidate`, `Trailing Candidate`: The names of the winner and the runner-up.
    *   `Margin`: The vote difference between the leading and trailing candidates.
    *   `Status`: The final result status (e.g., "Result Declared").
    *   `State ID`, `State`: Identifiers for the state to which the constituency belongs.

*   **`constituencywise_details.csv`**: This file provides a granular breakdown of votes for every candidate in each constituency.
    *   `S.N.`, `Candidate`, `Party`: Details of each candidate.
    *   `EVM Votes`, `Postal Votes`, `Total Votes`: Vote counts from Electronic Voting Machines and postal ballots.
    *   `% of Votes`: The percentage of the total votes secured by the candidate.
    *   `Constituency ID`: A unique identifier for the constituency.

*   **`partywise_results.csv`**: This file summarizes the performance of each political party.
    *   `Party`, `Party ID`: The name and unique identifier for each party.
    *   `Won`: The total number of seats won by the party.

*   **`states.csv`**: A reference file linking State IDs to State names.
    *   `State ID`, `State`: Unique identifier and name for each state.

## Methodology

The creation of the interactive dashboard involved the following steps:

1.  **Data Cleaning & Preparation**: The raw CSV files were meticulously cleaned to ensure data consistency and accuracy. This included handling missing values, correcting data types, and standardizing names.
2.  **Data Import**: The cleaned CSV files were imported into a data analysis tool (e.g., Power BI, Tableau).
3.  **Data Modeling**: An Enhanced Entity-Relation (EER) diagram was created to establish logical relationships between the different tables, ensuring data integrity and enabling complex queries.
4.  **Creating KPIs**: Key Performance Indicators (KPIs) were developed to summarize crucial information, such as total seats, vote share percentages, and alliance-wise performance.
5.  **Dashboard Creation**: Interactive visualizations and dashboards were built to present the data in an intuitive and user-friendly manner. This included creating multiple navigable pages for different levels of analysis.

## Dashboard Snapshots

Here is a breakdown of the key pages in our interactive dashboard:

### Landing Page
![Landing Page](https://github.com/CecilEkka/India-General-Election-Analysis-2024/blob/main/Dashboard_Images/1.%20Landing_Page.png)
This is the main entry point of the dashboard. It provides a brief introduction to the project and features navigation buttons that allow users to jump to specific analysis pages:
*   Overview Analysis
*   State Demographics
*   Constituency Analysis
*   State Analysis

### Overview Analysis
![Overview Analysis](https://i.imgur.com/v8tT9oO.png)
This page offers a high-level summary of the election results, breaking down the performance of the major political alliances:
*   **NDA (National Democratic Alliance)**: Total seats won and percentage share.
*   **I.N.D.I.A (Indian National Developmental Inclusive Alliance)**: Total seats won and percentage share.
*   **Others**: Seats won by parties not belonging to the two major alliances.

### State Demographics Analysis
![State Demographics Analysis][(https://i.imgur.com/4zYgO2G.png)](https://github.com/CecilEkka/India-General-Election-Analysis-2024/blob/main/Dashboard_Images/7.State_Demographics_Analysis.png)
This dashboard provides a visual representation of the election results across India using three distinct maps:
*   **Left Map**: A state-wise analysis showing overall performance.
*   **Middle Map**: A constituency-wise analysis, offering a more detailed view.
*   **Right Map**: A map indicating which major alliance secured the majority of seats in each state.

### State Analysis
![State Analysis](https://i.imgur.com/dK3fR1O.png)
This page allows for a deep dive into the election results on a state-by-state basis. Users can select a state to view detailed party-wise performance and seat distribution within that state.

### Constituency Analysis
![Constituency Analysis](https://i.imgur.com/p5p6l0T.png)
This page offers a micro-level analysis of individual constituencies. Users can select a constituency to view:
*   Total votes, EVM votes, and postal votes.
*   Detailed information about the winning candidate, runner-up, and second runner-up, including their party affiliation and vote share.

## Enhanced Entity-Relation (EER) Diagram
![EER Diagram](https://i.imgur.com/8QO9y8B.png)

The EER diagram illustrates the relationships between the tables in our database:

*   **`constituencywise_results`** has a one-to-many relationship with **`constituencywise_details`**, as one constituency has multiple candidates.
*   **`constituencywise_results`** is linked to **`partywise_results`** through the `Party_ID`, establishing a connection between the winning party of a constituency and the party's overall performance.
*   **`statewise_results`** connects to **`constituencywise_results`** on constituency names and to the **`states`** table via `State_ID`, allowing for state-level aggregation and analysis.

## SQL Analysis

The attached PDF file, **"INDIA GENERAL ELECTIONS RESULT ANALYSIS 2024.pdf"**, contains a detailed analysis performed using SQL. The queries cover a range of questions, from basic seat counts to more complex analyses of candidate performance and vote distribution. This SQL-based analysis forms the backbone of the data presented in the dashboard.
