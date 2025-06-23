# Lede Project 1: Import of Maritime Aquarium Fishes to Germany decreases, but is still on a high level

This is my submission of my first project during the Lede Program for Data Journalism (https://ledeprogram.com/). 

## Aim

Wild-caught fish for marine aquariums are a threat to the ecosphere. In recent years, however, there has been a sustainability trend in the German aquarium scene - the purchase of wild-caught corals and fish has been discredited, at least in part. I wanted to find out: Is this supposed trend reflected in the trade data and has the import of live ornamental marine fish actually declined?

## Proceeding

### Data Sources

I mainly used trade data from [Statistisches Bundesamt in Germany](https://www-genesis.destatis.de/datenbank/online). They collect statistics on imports and exports of almost 15,000 products to Germany, among them "live ornamental marine fish". Some of the documents can be downloaded as CSV, but I used the API of the authority. Before starting the analysis, one has to set up a (free) account and an API Key.

In addition, I used data of GDP per capita from the world bank which I downloaded as a CSV. You can find the raw data [in my repository](https://github.com/sophiabmnn/Project_1/blob/main/gdp_percapita_raw.csv).

### Analysis

Please be aware that the analysis requires several Python packages, including requests, pandas, dotenv, os, xmltodict, StringIO, numpy, deep_translator.

As a first step, I retrieved a very general table of trade data from the Statistisches Bundesamt API. I filtered it for "live ornamental marine fish" and for the years I wanted to focus my analysis - 2013 to 2023. 

In a second step, I retrieved a more specialized dataset from Statistisches Bundesamt showing which countries the fishes are exported from.

Finally, I merged the dataset with data of GDP per capita from World Bank.

You can find my [Notebook](https://github.com/sophiabmnn/Project_1/blob/main/Project1_TradewithSeaFishes.ipynb) here.

### Results

My analysis showed that there was actually a decrease in the import of live ornamental marine fish, comparing 2013 with 2023. However, the numbers are still on a high level. 

Detailed findings - [one table](https://github.com/sophiabmnn/Project_1/blob/main/fishes.csv) showing the general trends and [one table](https://github.com/sophiabmnn/Project_1/blob/main/fishes_countrygdp.csv) showing the exporting countries and respective GDPs - are saved in this repository as well.

## Learnings

The most difficult part of this analysis was retrieving the data from the API of Statistisches Bundesamt. The documentation is really extensive, but still it was difficult to figure out which parameters I could use to get the data I want to have. In addition, cleaning the data in pandas took some time - as they were quite untidy when I finally received them.

If I had more time, I would like to compare these trends in Germany to data from other countries. In addition, I would be interested in how the trade with corals changed over the past years.