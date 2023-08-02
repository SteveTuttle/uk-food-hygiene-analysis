# nosql-challenge
UNC_data_bootcamp_module_12

## Challenge Description
### Background
> The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

***from the UNC Bootcamp instructions for this challenge***

## Deliverables



### Part-1: Database and Jupyter Notebook Set Up
For this part of the challenge I will be using __NoSQL_setup_starter.ipynb__ which I have renamed ***NoSQL_setup_SDT.ipynb*** going forward. To accomplish this part of the challenge of we must complete the following steps as per challenge instructions:
1) Import the data provided in the _establishments.json_ file from your Terminal. Name the database _uk_food_ and the collection _establishments_. Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.
2) Within your notebook, import the libraries you need: __PyMongo and Pretty Print__.
3) Create an instance of the __Mongo Client__.
4) Confirm that you created the database and loaded the data properly:
  * List the databases you have in MongoDB. Confirm that _uk_food_ is listed.
  * List the collection(s) in the database to ensure that _establishments_ is there.
  * Find and display one document in the _establishments_ collection using _find_one_ and display with _pprint_.
5) Assign the _establishments_ collection to a variable to prepare the collection for use.

#### Requirement-1





### Part-2: Update the Database
> The magazine editors have some requested modifications for the database before you can perform any queries or analysis for them.

***from the UNC Bootcamp instructions for this challenge***

For this part of the challenge I will continue to use NoSQL_setup_SDT.ipynb we must make the following changes to the establishments collection per challenge instructions to complete the challenge:
1) Add the following information to the database:

|--------------------------------------------------------------------------|
|  {                                                                       | 
|      "BusinessName":"Penang Flavours",                                   |
|      "BusinessType":"Restaurant/Cafe/Canteen",                           |
|      "BusinessTypeID":"",                                                |
|      "AddressLine1":"Penang Flavours",                                   |
|      "AddressLine2":"146A Plumstead Rd",                                 |
|      "AddressLine3":"London",                                            |
|      "AddressLine4":"",                                                  |
|      "PostCode":"SE18 7DY",                                              |
|      "Phone":"",                                                         |
|      "LocalAuthorityCode":"511",                                         |
|      "LocalAuthorityName":"Greenwich",                                   |
|      "LocalAuthorityWebSite":"http://www.royalgreenwich.gov.uk",         |
|      "LocalAuthorityEmailAddress":"health@royalgreenwich.gov.uk",        |
|      "scores":{                                                          |
|          "Hygiene":"",                                                   |
|          "Structural":"",                                                |
|          "ConfidenceInManagement":""                                     |
|      },                                                                  |
|      "SchemeType":"FHRS",                                                |
|      "geocode":{                                                         |
|          "longitude":"0.08384000",                                       |
|          "latitude":"51.49014200"                                        |
|      },                                                                  |
|      "RightToReply":"",                                                  |
|      "Distance":4623.9723280747176,                                      |
|      "NewRatingPending":True                                             |
|  }                                                                       |
|--------------------------------------------------------------------------|

2) Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.
3) Update the new restaurant with the BusinessTypeID you found.
4) The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.
5) Some of the number values are stored as strings, when they should be stored as numbers.
  1) Use update_many to convert latitude and longitude to decimal numbers.
  2) Use update_many to convert RatingValue to integer numbers.

#### Requirement-2


### Part-3: Exploratory Analysis



#### Requirement-3



## Resources
### Bootcamp References -- update later with challenge data
Module 12 Instructions
 
starter_code
* NoSQL_analysis_starter.ipynb
* NoSQL_setup_starter.ipynb

Resources
* establishments.json

Example Data:
 
output_data _(original folder)_
* cities.csv
* Fig1.png

 
***Special Thanks:***
* Jamie Miller
* Mounika Mamindla
* Lisa Shemanciik
 
### External References
_(where possible will provide link to website)_
* [citypy library](https://github.com/wingchen/citipy)
* OpenWeatherMap documentation & API
* geoapify documentation & API
* [pandas documentation](https://pandas.pydata.org/docs/reference/general_functions.html)
* [matplotlib documentation](https://matplotlib.org/stable/index.html)
* [hvplot documentation](https://hvplot.holoviz.org/reference/geopandas/points.html)
* [scipy.stats documentation](https://docs.scipy.org/doc/scipy/reference/stats.html)


