# nosql-challenge
UNC_data_bootcamp_module_12

## Challenge Description
### Background
> The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

***from the UNC Bootcamp instructions for this challenge***

## Deliverables
To complete this challenge I will be using MongoDB Compass and Jupyter Notebooks. This challenge is broken down into three parts, the details of each come from the BootCamp Instructions so there are no questions what I intend to accomplish. The three parts of this challenge are as follows:
* Database and Jupyter Notebook Set Up
* Update the Database
* Exploratory Analysis

### Part-1: Database and Jupyter Notebook Set Up
For this part of the challenge I will be using __NoSQL_setup_starter.ipynb__ which I have renamed ***NoSQL_setup_sdt.ipynb*** going forward. To accomplish this part of the challenge of we must complete the following steps as per challenge instructions:
1) Import the data provided in the _establishments.json_ file from your Terminal. Name the database _uk_food_ and the collection _establishments_. Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.
2) Within your notebook, import the libraries you need: __PyMongo and Pretty Print__.
3) Create an instance of the __Mongo Client__.
4) Confirm that you created the database and loaded the data properly:
  * List the databases you have in MongoDB. Confirm that _uk_food_ is listed.
  * List the collection(s) in the database to ensure that _establishments_ is there.
  * Find and display one document in the _establishments_ collection using _find_one_ and display with _pprint_.
5) Assign the _establishments_ collection to a variable to prepare the collection for use.


### Part-2: Update the Database
> The magazine editors have some requested modifications for the database before you can perform any queries or analysis for them.

***from the UNC Bootcamp instructions for this challenge***

For this part of the challenge I will continue to use __NoSQL_setup_sdt.ipynb__ and make the following changes to the _establishments_ collection per challenge instructions to complete the challenge:
1) Add the following information to the database:

```
{
    "BusinessName":"Penang Flavours",
    "BusinessType":"Restaurant/Cafe/Canteen",
    "BusinessTypeID":"",
    "AddressLine1":"Penang Flavours",
    "AddressLine2":"146A Plumstead Rd",
    "AddressLine3":"London",
    "AddressLine4":"",
    "PostCode":"SE18 7DY",
    "Phone":"",
    "LocalAuthorityCode":"511",
    "LocalAuthorityName":"Greenwich",
    "LocalAuthorityWebSite":"http://www.royalgreenwich.gov.uk",
    "LocalAuthorityEmailAddress":"health@royalgreenwich.gov.uk",
    "scores":{
        "Hygiene":"",
        "Structural":"",
        "ConfidenceInManagement":""
    },
    "SchemeType":"FHRS",
    "geocode":{
        "longitude":"0.08384000",
        "latitude":"51.49014200"
    },
    "RightToReply":"",
    "Distance":4623.9723280747176,
    "NewRatingPending":True
}
```

2) Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the _BusinessTypeID_ and _BusinessType_ fields.
3) Update the new restaurant with the _BusinessTypeID_ you found.
4) The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.
5) Some of the number values are stored as strings, when they should be stored as numbers.
 * Use _update_many_ to convert _latitude_ and _longitude_ to decimal numbers.
 * Use _update_many_ to convert _RatingValue_ to integer numbers.


### Part-3: Exploratory Analysis
> Eat Safe, Love has specific questions they want you to answer, which will help them find the locations they wish to visit and avoid.

***from the UNC Bootcamp instructions for this challenge***

For the final part of the Challenge I will open __NoSQL_analysis_starter.ipynb__ and rename it __NoSQL_analysis_sdt.ipynb__, then I will follow the instructions and notes from the Challenge that I need to be aware of throughout the dataset listed below:

* _RatingValue_ refers to the overall rating decided by the Food Authority and ranges from 1-5. The higher the value, the better the rating.
 * __Note:__ This field also includes non-numeric values such as 'Pass', where 'Pass' means that the establishment passed their inspection but isn't given a number rating. We will coerce non-numeric values to nulls during the database setup before converting ratings to integers.
* The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. This means, the higher the value, the worse the establishment is in these areas.

Use the following questions to explore the database, and find the answers, so you can provide them to the magazine editors.

Unless otherwise stated, for each question:
* Use _count_documents_ to display the number of documents contained in the result.
* Display the first document in the results using _pprint_.
* Convert the result to a Pandas DataFrame, print the number of rows in the DataFrame, and display the first 10 rows.

1) Which establishments have a hygiene score equal to 20?

2) Which establishments in London have a _RatingValue_ greater than or equal to 4?

__Hint:__ The London Local Authority has a longer name than "London" so you will need to use _$regex_ as part of your search.

3) What are the top 5 establishments with a _RatingValue_ of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?

__Hint:__ You will need to compare the geocode to find the nearest locations. Search within 0.01 degree on either side of the latitude and longitude.

4) How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.

__Hint:__ You will need to use the _aggregation_ method to answer this.


## Resources
### Bootcamp References
Module 12 Instructions
 
starter_code
* NoSQL_analysis_starter.ipynb
* NoSQL_setup_starter.ipynb

Resources
* establishments.json
 
***Special Thanks:***
* Jamie Miller
* Mounika Mamindla
* Lisa Shemanciik
 
### External References
_(where possible will provide link to website)_
* [pandas documentation](https://pandas.pydata.org/docs/reference/general_functions.html)
* [MongoDB documentation](https://www.mongodb.com/docs/)
* [SQL to MongoDB Mapping Chart](https://www.mongodb.com/docs/manual/reference/sql-comparison/)
* [PyMongo documentation](https://pymongo.readthedocs.io/en/stable/index.html)
* YouTube
* Google
