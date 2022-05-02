# Tweet Classifier Project

### Table of Contents

- [Tweet Classifier Project](#tweet-classifier-project)
    - [Table of Contents](#table-of-contents)
  - [Project Motivation<a name="motivation"></a>](#project-motivation)
  - [Installation <a name="installation"></a>](#installation-)
  - [Data](#data)
    - [Data Advise](#data-advise)
  - [File Descriptions <a name="files"></a>](#file-descriptions-)
  - [Instructions:](#instructions)
  - [Licensing, Authors, Acknowledgements<a name="licensing"></a>](#licensing-authors-acknowledgements)
  - [Next Possibles Steps](#next-possibles-steps)

## Project Motivation<a name="motivation"></a>

This Project analyse data and implements machine learning model to predict how much someone will spend based on demographics and offer type.

### Introduction

The analysed dataset contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). Some users might not receive any offer during certain weeks. 

Not all users receive the same offer, and that is the challenge to solve with this data set.

Our task is to combine transaction, demographic and offer data to determine which demographic groups respond best to which offer type. This data set is a simplified version of the real Starbucks app because the underlying simulator only has one product whereas Starbucks actually sells dozens of products.

Every offer has a validity period before the offer expires. As an example, a BOGO offer might be valid for only 5 days. You'll see in the data set that informational offers have a validity period even though these ads are merely providing information about a product; for example, if an informational offer has 7 days of validity, you can assume the customer is feeling the influence of the offer for 7 days after receiving the advertisement.

You'll be given transactional data showing user purchases made on the app including the timestamp of purchase and the amount of money spent on a purchase. This transactional data also has a record for each offer that a user receives as well as a record for when a user actually views the offer. There are also records for when a user completes an offer. 

Keep in mind as well that someone using the app might make a purchase through the app without having received an offer or seen an offer.

### Example

To give an example, a user could receive a discount offer buy 10 dollars get 2 off on Monday. The offer is valid for 10 days from receipt. If the customer accumulates at least 10 dollars in purchases during the validity period, the customer completes the offer.

However, there are a few things to watch out for in this data set. Customers do not opt into the offers that they receive; in other words, a user can receive an offer, never actually view the offer, and still complete the offer. For example, a user might receive the "buy 10 dollars get 2 dollars off offer", but the user never opens the offer during the 10 day validity period. The customer spends 15 dollars during those ten days. There will be an offer completion record in the data set; however, the customer was not influenced by the offer because the customer never viewed the offer.

## Installation <a name="installation"></a>

* [Python 3] - All code and notebooks were develop in python 3.8
* [Jupyter Notebook] - jupyter notebook is an open source and used to data analyze with python code
* [Pandas] - uses to clean, organize, convert, and merge the data.
* [numpy] - is a fundamental scientific computing.
* [sklearn] - uses for ML tasks.
* [matplotlib] and [seaborn] - uses to create beatifull data graphs.
* [imblearn] - to balance our data.



# Data Sets

The data ais contained in three files:

* portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)
* profile.json - demographic data for each customer
* transcript.json - records for transactions, offers received, offers viewed, and offers completed

Here is the schema and explanation of each variable in the files:

**portfolio.json - (10 offers x 6 fields)**
* id (string) - offer id
* offer_type (string) - type of offer ie BOGO, discount, informational
* difficulty (int) - minimum required spend to complete an offer
* reward (int) - reward given for completing an offer
* duration (int) - time for offer to be open, in days
* channels (list of strings)

**profile.json  - (17000 users x 5 fields)**
* age (int) - age of the customer 
* became_member_on (int) - date when customer created an app account
* gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* id (str) - customer id
* income (float) - customer's income

**transcript.json - (306648 events x 4 fields)**
* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours since start of test. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record

## File Descriptions <a name="files"></a>

- data: Data CSVs
- startbucks_offer_analysis.ipynb: Offer analysis notebook.


## Licensing, Authors, Acknowledgements<a name="licensing"></a>

This code uses the MIT License. feel free to use the code as you would like!


## Next Possibles Steps

- Optmize our person spent class prediction.
- Separe spent class per pesonas to identify with offer match more with each class.