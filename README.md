# ARCOS

## Introduction
The Automated Reports and Consolidated Ordering System (ARCOS), is a data collection system used by manufacturers and distributors to report controlled substances transactions to the Drug Enforcement administration. In this project I will be exploring specifically opioid sales and distribution data published from this system as a result of an Ohio federal court ruling. The dataset allows the tracking of opioid pain pills from distributors to pharmacies and practitioners in the US from 2006 to 2012.

## Dataset Details
Two versions of this data are available online. The original is over 150GB in size and contains transaction records relating to all controlled substances being transferred between distributors and pharmacies. The filtered dataset here created by the Washington Post, focuses on opioid medications and is around 75GB in total size, containing approximately 178 million rows. Due to the size of this dataset and the very slow query times I was experiencing using it, I created a third version which is reduced down to only include rows where the purchasing organizations are located within the state of Massachusetts, which reduced the dataset down to around 2.5 million rows.

Both files are offered as a single CSV files and contain 42 columns comprised of information relating to three categories. The first is information about the buyer and seller, the business names, address, city, state, zip and county for both the pill distributor and buying entity. The second category is details on the drug being transferred, the type of pill, quantity of packs or bottles, quantity of pills, strength, etc. The final category is related specifically to the transaction, the date it took place, order form number, transaction id and code and correction number.

## Data Warehouse
To determine the scope of the data warehouse, I started by defining business questions the warehouse will be used to answer. 
•	Which distributors supplied the most pills and did this change from month to month or year to year?
•	What percent of the total is each distributor responsible for?
•	Was there an even distribution in pills received throughout the state or concentrations in areas?
•	Did the overall pill counts fluctuate between various months or years?
•	Did the doses by type of drug increase over time?

Looking at these questions from a time perspective, I decided the warehouse would only need to store data aggregated at the month level at a minimum. It will need to include information related to the distributor’s and buyer’s locations and data for the number of boxes, pills and grams of active medication.
