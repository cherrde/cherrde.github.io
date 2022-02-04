# Project Overview
Sparkify has a series of json files containing data that they would like analyzed. this data concerns songs and user activity on a new music streaming app. The team is interested in the songs users are listening to on the app. They would like a database optimized to the queries they would like to run particularly concerning aspects of the user interactions with songs.
To this end, we are building a Redshift cluster on a star schema with a fact table and several
# Schema Design Considerations and Justification
The schema is essentially a star schema with a central fact table for the songplays referencing the users, songs, artists, and time data. Some minor data analysis was performed on a few files to ensure the column sizes were adequate for the data being stored. Datatypes were chosen to make aggregation quick if numerical (int or float as appropriate), dates stored in proper date format or strings stored in appropriate length fields. Some room for growth of the data (length of some textual ids for example or longer song titles or user_agent values). The data from the json files was viewed to determine the appropriate data type and size as noted.
# File List
- dwh.cfg - a configuration file containing information for connection to a Redshift cluster and S3 buckets where data resides
- create_tables.py - a python script that drops (if exists) and creates the sparkifydb
- etl.py - a python script that automates the etl.ipynb processes tested in the jupyter notebooks
- README.md - this markdown file
- sql_queries.py - a python file containing a library of SQL queries to select, insert, create or drop tables
# Installation
No installation required. Python 3.0 used for this project.
# Running the Files
In terminal console run the create_tables.py to create (or drop and recreate) the dev schema:
    python create_tables.py
In a terminal console run the etl.py script to load all the data from the data directories into the database schema
    python etl.py
# Further investigation
Build aggregate queries to generate the data the customer wishes to view.
