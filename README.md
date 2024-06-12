# NoSQL Challenge: UK Food Standards Agency Data Analysis
Repository: nosql-challenge
## Overview
This project involves analyzing food hygiene ratings data from the UK Food Standards Agency to assist the magazine "Eat Safe, Love" in identifying establishments for future articles. The following steps were completed to achieve the project goals.

## Project Setup
Repository Creation: A new repository called nosql-challenge was created and cloned to the local machine.
File Setup: Jupyter notebook starter files and the Resources folder containing establishments.json were added to the repository. Changes were pushed to GitHub.

### Part 1: Database and Jupyter Notebook Set Up
Data Import: The data from establishments.json was imported into a MongoDB database named uk_food with a collection named establishments.
Library Imports: The necessary libraries, PyMongo and Pretty Print (pprint), were imported.
Mongo Client Instance: An instance of the Mongo Client was created, and the database and data import were confirmed by listing the databases and collections and displaying a document from the collection.

### Part 2: Database Updates
New Restaurant Addition: A new restaurant, "Penang Flavours," was added to the database with the following details:

json
Copy code
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
    "RightToReply": "",
    "Distance": 4623.9723280747176,
    "NewRatingPending": True
}
BusinessTypeID Update: The BusinessTypeID for "Restaurant/Cafe/Canteen" was retrieved and updated for the new restaurant.

Document Deletion: All documents related to the Dover Local Authority were identified and removed from the database.

Field Conversion: The latitude and longitude fields were converted to decimal numbers, and the RatingValue field was converted to integers using update_many.

### Part 3: Exploratory Analysis
Hygiene Score of 20: Establishments with a hygiene score of 20 were identified and analyzed.

London Establishments with High Ratings: Establishments in London with a RatingValue of 4 or higher were found and analyzed.

Top 5 Establishments Near "Penang Flavours": The top 5 establishments with a RatingValue of 5, sorted by the lowest hygiene score and located near "Penang Flavours," were identified.

Hygiene Score of 0 Analysis: The number of establishments with a hygiene score of 0 in each Local Authority area was counted, and the top ten areas were listed.
