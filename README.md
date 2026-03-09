# macro_modeling_materials

This repository is licensed under CC BY-NC 4.0.
Commercial use is prohibited without permission.

The code supplied in this repo follow in the steps below in the production of the the macroeconomic models linking population change (desirability) to larger macroeconomic shifts.

## Primary Process:

### Population-based models:

1-global_implications_tile_data_create_exactextract.Rmd (code available in repo)
- Pulling high resolution data and converting it to 12.5 km grid. Create dataset of variables for each 12.5km grid 
- Variables include population, urban-rural continuum, gross domestic product, human development index, poverty (deprivation index), and age and sex 

2-global_implications_tile_data_prep.Rmd (code available in repo)
- Data cleaning, exclusions, calculating change variables for 20 years

3-global_implications_tile_data_models.Rmd (code available in repo)
- Bivariate linear models for the relationship between population change and sociodemographic and economic changes (for variables at 12.5 km resolution)
- Modeled separately by ECON AND URBAN classification or ECONOMY classification  
- Produces coefficient table
- Produces plots for comparison
  
4-global_implications_national_data_create.Rmd (code available in repo)
- Merge and create dataset for national-level macroeconomic variables including: GDP, GDP per capita, residential property price index (RPPI), commercial property price index (CPPI), price living index (PLI), debt to income ratio (DTI), unemployment, income, and nativity 

5-global_implications_national_data_models.Rmd (code available in repo)
- Bivariate linear models for the relationship between national-level GDP change and macroeconomic change GDP-MEV coefficients by regional economy are produced in code
- Coefficients are then applied to POP-GDP coefficients to estimate the indirect (mediating effect) of POP - GDP - MEV 
- Produces final coefficient table
- Produces plots (forest and continuous)

## Severe climate exposure (DID) 

1-GDP_FireFloodWind_DID_Danielle.Rmd (code available in repo)
- Links global GDP (12.5 km) data with climate exposures (flood, fire, wind) and runs difference-in-differences models for annual change in GDP post-event 
- Several versions of models are available (overall, by economy, by economy and urban-rural), and output can be found here
- We evaluate changes in the following 10-years after a severe event and divide into three periods (0-3, 4-6, 7-10 years)

2-DiD MEV national estimation.Rmd (code available in repo)
- Translates Climate-GDP changes to MEV changes (RRPI, CPPI, DTI, Income) by applying national-level GDP-MEV relationships (indirect, mediation approach) 
- Produces final coefficient table
