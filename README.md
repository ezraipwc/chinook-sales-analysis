# Chinook Sales Analysis
*Business Data Analysis Project using PostgreSQL and Python*

## Introduction

This project analyzes the Chinook database, a relational database for a digital media store. PostgreSQL is used for querying chinook database, while Python is used for data extraction and visualization.

This project aims at demonstrating procedures in data analysis:

* Examing the schema of database
* Querying SQL queries by JOIN, GROUP BY, ORDER BY, linking primary keys between tables
* Importing SQL query results into Jupyter notebook via pandas
* Visualizing data with matplotlib, seaborn and squarify
* Intepreting findings from data

The intepretation of data is guided under the following directions:
* How the categories of the products affect sales, i.e. how artist, genre influence sales.
* The traits of the buyers (Who are the top buyers? What countries are they from?).
* How revenue changes over time.

---

## Tools Used
For SQL query:
* PostgreSQL
* DBeaver

For linking SQL with Python:
* SQLAlchemy
* python-dotenv

For data analysis:
* Python
* Jupyter
* pandas
* numpy
* matplotlib
* seaborn
* Squarify

---

## About Dataset

The Chinook data was obtained at https://github.com/lerocha/chinook-database on May 3 2026. A copy of the data has also been included in this project.

This relational database represents a digital media store. There are 11 tables: invoice_line, invoice, customer, employee, track, album, artist, genre, playlist_track, playlist, and media_type. Although it mimics a digital store structurally, the data was synthetically generated. This project serves to demonstrate the workflow of ecommerce data analysis rather than the realistic trends of the current digital media industry.

---

## Structure of Project Folder

chinook/
├── chinook.ipynb
├── README.md
├── data/
│    └── Chinook_PostgreSql.sql
├── img/
     └── img/chinook_schema.png

The project notebook is chinook.ipynb. The sql file used in this project can be found under *data* folder. Database credentials are stored locally and excluded from this project.


---

## Database Setup
PostgreSQL 18 installed and managed by DBeaver. A new database called "chinook" was created with the "Chinook_PostgreSql.sql" file.

---

## Summaries of Results

1. What are the top artists by revenue?

Obtained by joining 4 tables: invoice_line, track, album, and artist.

Findings: 
* Of total 165 artists, the top 5 artists by revenue are **Iron Maiden**, **U2**, **Metallica**, **Led Zeppelin**, and **Lost**.
* These top 5 artists contribute 21.57% of total revenue.
* Sales are not dominated by the performance of the top artists.

---

2. What are the best selling genres?

Findings:
* Of total 25 genres, the top 5 genres by revenue are **Rock**, **Latin**, **Metal**, **Alternative & Punk**, and **TV shows**.

Obtained by joining 3 tables; invoice_line, track, and genre.
* The top 5 genres contribute 78% of total revenues.
* Sales are dominated by top performaning genres.

---

3. Which countries generate the most revenue?

Findings:
* The top 3 countries are **USA**, **Canada**, and **France**. 
* The top 3 countries comprise 44% of total market revenues.
* The market distribution across the world is relatively diversified. 
* There are markets in South America (~8.16%), as well as India (~3.23%) but not Asia-Pacific, Middle-East or Africa.

---

4. Which countries look strongest after normalizing revenue by customer and by invoice?

This question arose as Canadian revenue is 60% of US revenue while having just 10% of US population.  To answer the trend, normalization of revenue by customer and invoice in each country are done.

Purpose:
* Identify purchasing power of customers from each country
* Identify whether their purchasing powers are due to high transaction volume, high purchase power in each transaction, or higher customer base.

Findings:
* The higher customer base per population in Canada solely drives the disproportionately high sales compared to the US.
* Purchasing power or transaction volume do not account for the disproportionate distribution of revenue.

---

5. Who are the Top Buyers?

Findings:
* The distribution of revenue among buyers are relatively the same.
* Measure of central tendancies revealed a relatively 
* The purchasing frequency distributions among the buyers are mostly unique.

---

6. What do top 5 buyers purchase?

A substudy on the preferences of genres, 
artists and albums for top 5 buyers. 

---

7. How does revenue change over time?

Study the sales performance by quarter.

Findings:
* Relatively stable quarterly revenue with isolated spikes.
* Spike quarters are driven by average transaction totals in each bill (r=0.947) rather than more counts of transactions (r=0.339), as demonstrated in Pearson correlation.

---

## Future Plans

* Create dashboard using Power BI/Tableau
* More regional purchase behavioural comparison (e.g. by continent)
* Cohort-style customer analysis with realistic data