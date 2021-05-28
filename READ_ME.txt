READ ME!

Step 1.
To acces the Dataset a API key from the Danish Buisness Authority (Virk) have to be obtained.

Step 2:
use the querry below through your prefered framework to extract all companies created between 15/03-2018 and 15/03-2021 through your prefered framework.
Gather the different JSON files in a folder containing the From Json to CSV file.


query:

http://distribution.virk.dk/cvr-permanent/virksomhed/_search

{
    "_source":[
    "Vrvirksomhed.cvrNummer",
    "Vrvirksomhed.virksomhedMetadata.nyesteNavn.navn",
    "Vrvirksomhed.virksomhedMetadata.nyesteBeliggenhedsadresse",
    "Vrvirksomhed.virksomhedMetadata.stiftelsesDato"
  ],
  "query":{
    "range":{"Vrvirksomhed.virksomhedMetadata.stiftelsesDato":{"gte":"2020-03-15", "lte": "2020-04-01"}}
  },
  "size":200
}

{
    "_source":[
    "Vrvirksomhed.cvrNummer",
    "Vrvirksomhed.virksomhedMetadata.nyesteNavn.navn",
    "Vrvirksomhed.virksomhedMetadata.nyesteBeliggenhedsadresse",
    "Vrvirksomhed.virksomhedMetadata.stiftelsesDato",
    "Vrvirksomhed.hovedbranche",
    "Vrvirksomhed.virksomhedMetadata.nyesteVirksomhedsform",
    "Vrvirksomhed.virksomhedMetadata.sammensatStatus",
    "Vrvirksomhed.virksomhedsstatus"
  ],
  "query":{
    "range":{"Vrvirksomhed.virksomhedMetadata.stiftelsesDato":{"gte":"2018-03-15", "lte": "2018-04-05"}}
    
  },
  "size":3000
}


After data extraction, use the "From JSON to CSV" to merge all the Obtained JSON files from the querry into one CSV file.

The files "NN for Company form (Kortbeskrivelse).ipynb", "NN for Status.ipynb", "Random-Forest-on-Kortbeskrivelse-BDP-VIRK-Dataset-28.05.ipynb", 
"Random-Forest-on-Status-BDP-VIRK-Dataset-28.05.ipynb", "Multible Linear Regression on Kortbeskrivelse.ipynb", are files containing machine learning
algorithms manipulating and modeling the final dataset.

"NN for Company form (Kortbeskrivelse).ipynb", "NN for Status.ipynb":
Neural network Models, supervised machine learning algorithms making prediction on if the company is an ApS and the Status of the comapny.

"Random-Forest-on-Kortbeskrivelse-BDP-VIRK-Dataset-28.05.ipynb", "Random-Forest-on-Status-BDP-VIRK-Dataset-28.05.ipynb":
Random forest modeling on the best split of features for predicting if the company is an ApS and the Status.

"Multible Linear Regression on Kortbeskrivelse.ipynb":
Multiple Linear Regression modelling upon wheter it is an ApS or not, along with a PCA analysis for feature relevance.

