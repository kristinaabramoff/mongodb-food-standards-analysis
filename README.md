# MongoDB: UK Food Standard Analysis



## Overview

This project analyzes food hygiene ratings data from the UK Food Standards Agency to assist the magazine *Eat Safe, Love* in identifying noteworthy establishments for future articles. Using MongoDB, PyMongo, and data from JSON files, the project involves database setup, updates, and exploratory data analysis to uncover insights into food hygiene standards across various locations.

---

## Project Setup

- **Repository Creation**: A new repository called `nosql-challenge` was created and cloned to the local machine.
- **File Setup**: Jupyter Notebook starter files and the `Resources` folder containing `establishments.json` were added to the repository. All changes were pushed to GitHub.

---

## Part 1: Database and Jupyter Notebook Setup

**File Used:** `NoSQL_setup_starter.ipynb`

- **Data Import**: The data from `establishments.json` was imported into a MongoDB database named `uk_food` with a collection named `establishments`.
- **Library Imports**: Necessary libraries, including PyMongo and Pretty Print (`pprint`), were imported.
- **Mongo Client Instance**: An instance of the Mongo Client was created, and the database and data import were verified by listing the databases, collections, and displaying a document from the collection.

---

## Part 2: Database Updates

**File Used:** `NoSQL_setup_starter.ipynb`

- **New Restaurant Addition**: A new restaurant, *Penang Flavours*, was added to the database with details such as business type, address, geocode, and a pending rating status.

```json
{
    "BusinessName": "Penang Flavours",
    "BusinessType": "Restaurant/Cafe/Canteen",
    "BusinessTypeID": "",
    "AddressLine1": "Penang Flavours",
    "AddressLine2": "146A Plumstead Rd",
    "AddressLine3": "London",
    "AddressLine4": "",
    "PostCode": "SE18 7DY",
    "Phone": "",
    "LocalAuthorityCode": "511",
    "LocalAuthorityName": "Greenwich",
    "LocalAuthorityWebSite": "http://www.royalgreenwich.gov.uk",
    "LocalAuthorityEmailAddress": "health@royalgreenwich.gov.uk",
    "scores": {
        "Hygiene": "",
        "Structural": "",
        "ConfidenceInManagement": ""
    },
    "SchemeType": "FHRS",
    "geocode": {
        "longitude": "0.08384000",
        "latitude": "51.49014200"
    },
    "Distance": 4623.97,
    "NewRatingPending": true
}
``` 

- BusinessTypeID Update: The correct BusinessTypeID for "Restaurant/Cafe/Canteen" was retrieved and updated for Penang Flavours.
- Document Deletion: All documents related to the Dover Local Authority were removed from the database.
- Field Conversion:
 The latitude and longitude fields were converted from strings to decimal numbers.
 The RatingValue field was converted from strings to integers using update_many.

## Part 3: Exploratory Data Analysis

**File Used:** `NoSQL_setup_starter.ipynb`

- Hygiene Score of 20: Established which establishments had a hygiene score of 20, analyzed their distribution and impact.
- London Establishments with High Ratings: Identified and analyzed establishments in London with a RatingValue of 4 or higher, using regex to match London-based locations.
- Top 5 Establishments Near Penang Flavours: Found the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, located nearest to Penang Flavours based on geocode proximity.
- Hygiene Score of 0 Analysis: Calculated the number of establishments with a hygiene score of 0 in each Local Authority area, listed the top 10 Local Authority areas by establishment count.
- 
## Key Technologies and Skills Demonstrated
- MongoDB/NoSQL: Hands-on experience with MongoDB for data management, including database creation, collection updates, and document manipulation.
- PyMongo: Used PyMongo to interface with MongoDB from Python, performing queries, updates, and data analysis.
- Data Cleaning: Applied field conversions and modifications (e.g., string to decimal) to ensure data accuracy and readiness for analysis.
- Geospatial Analysis: Performed proximity-based queries to analyze establishments near specific locations.
- Exploratory Data Analysis (EDA): Extracted insights through targeted queries and aggregation techniques, providing valuable findings for Eat Safe, Love.

  ## How to Use
  clone repository

- For database setup and updates, run NoSQL_setup_starter.ipynb.
- For exploratory data analysis, run NoSQL_analysis_starter.ipynb.
