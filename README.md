# Real Estate Rental Prices Prediction Project Overview

Have a look at this README file to get yourself up to date on the project, or find out how to set up the environment to commence the project.

## Table of Contents
1. [Repository Cloning](#1-Repository-Cloning)
2. [Install Dependencies](#2-Install-Dependencies)
3. [API Keys](#3-API-Keys)
4. [Data Sources](#4-Data-Sources)
5. [Data Scraping](#5-Data-Scraping)
6. [Data Preprocessing](#6-Data-Preprocessing)
7. [Model Building and Evaluation](#7-Model-Building-and-Evaluation)


## 1. Repository Cloning
In your IDE, run the following commands to clone the project repository:

```bash
git clone https://github.com/MAST30034-AppliedDataScience/project-2-group-real-estate-industry-project-34.git
cd project-2-group-real-estate-industry-project-34
```

## 2. Install Dependencies

Install the required packages by running:

```bash
pip install -r requirements.txt
```

## 3. API Keys

Several API keys are required to run various parts of this project. Follow the instructions below to obtain and set up each API key:

1. **Google Maps API Key**  
   - Sign up or log in at [Google Cloud Console](https://developers.google.com/maps/documentation/javascript/get-api-key).
   - Enable the Maps JavaScript API.
   - Add this key as `google_api_key` in `utilities.py`.

2. **OpenRouteService API Key**  
   - Register at [OpenRouteService](https://openrouteservice.org/sign-up/).
   - Generate an API key for location-based services.
   - Add this key to your environment file or `config/api_key.txt`.

3. **Domain.com.au API Key (for scraping property data)**  
   - Sign up for an account in [Domain Developers Portal](https://developer.domain.com.au/).
   - Then, go to projects and create a new project. 
   - After that, go to API Access and click on "Add API". Click "Add to Project" in Listings Management.
   - Create an OAuth Client, which gives you the client details and client secret, which you can use to access the API from the notebooks.
   - Use this for the `1_scrape.py` script for fetching property listings. You can create up to 3 projects under one account to scrape more data as Domain limits you to 500 pages per day per project.
   
Make sure to store your keys securely (such as in `.env` files) and never hardcode them directly in your scripts to avoid exposing sensitive information.

## 4. Data Sources

The project relies on various external datasets for analysis and modeling. Detailed information about each data source, including its origin, structure, and format, can be found in the `data/README.md` file located in the `data/` directory. 

This includes:
- **Geospatial Data**: Shapefiles containing SA2 boundaries for mapping and spatial analysis.
- **Rental Data**: Collected through web scraping, providing information on current rental prices, property attributes, and availability.
- **Demographic Data**: Population and income statistics from the Australian Bureau of Statistics (ABS), essential for forecasting trends in the housing market.
- **Crime Data**: Sourced from the Crime Statistics Agency, Victoria, to assess the impact of safety on property values.

Please refer to the `data/README.md` for a complete breakdown and the corresponding files used in the project.

## 5. Data Scraping

The project makes use of rental data scraped from domain. More information on this can be found in the scrape files in `notebooks`.

## 6. Data Preprocessing

Preprocessing steps for each dataset can be found in the preprocessing files in `notebooks`.

## 7. Model Building and Evaluation

Lastly, after joining all the data train a model to predict growth and demand. These models can be found in `models`.





