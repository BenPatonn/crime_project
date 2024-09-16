# Crime Project Pipeline and Unit Testing READ ME

## Read me for 'unit_tests_for_crime_project.py':

	1. Open in Vscode
 
	2. Input 'pytest unit_tests_for_crime_project.py' into terminal and press 'Enter'



## Read me for 'Crime Project pipeline.py': 

### A) Instructions for pipeline use:

	1. Download 'all_crime_data' folder and put into python directory
 
	2. Run 'Crime pipeline python.py' in Vscode
 
	3. 'Pipeline execution started...' will appear in terminal at start of pipeline
 
	4. 'LOG_FILE.txt' will appear in directory and will append errors and information
 
	5. 'Pipeline finished!' will appear in terminal once pipeline is completed
 
	  

### B) Data sets with original download sources (for data dictionary see link):

	1. Street dataset - 01/22-12/23 'Merseyside' and 'Nottinghamshire' files containing 'street' keyword
		https://data.police.uk/data/ 
  
	2. Outcome dataset - 01/22-12/23 'Merseyside' and 'Nottinghamshire' files containing 'outcome' keyword
		https://data.police.uk/data/ 
  
    	3. Stop and search (sas) dataset - 01/22-12/23 'Merseyside' and 'Nottinghamshire' files containing 'search' keyword
		https://data.police.uk/data/ 
  
    	4. Property dataset - year 2022
		https://www.gov.uk/government/statistical-data-sets/price-paid-data-downloads#yearly-file
  
    	5. LSOA dataset
		https://www.freemaptools.com/download-uk-postcode-lat-lng.htm
  
    	6. Population area dataset - 2022, 'MYE5' tab 
		https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates/datasets/populationestimatesforukenglandandwalesscotlandandnorthernireland
  
    	7. Deprivation dataset
		https://www.ons.gov.uk/datasets/create/filter-outputs/97ee5577-2246-4756-86ce-30712c35a418#get-data

### C) Reporting layer Outputs:
	Located in folder within directory:
	'/crime_data_outputs/aggregated_dataframes/'

	1. 'deprivation_LTLA_agg_output' - grouped by 'Local tier local authority'
 
	2. 'lsoa_broad_outcome_agg_output' - 3 dataframes merged (1,2,3 see section B), grouped by 'Falls within' and 'Broad Outcome Category'
 
	3. 'lsoa_crimetype_agg_output' - 3 dataframes merged (1,2,3 see section B), grouped by 'Falls within' and 'Crime type'
 
	4. 'lsoa_postcode_agg_output' - 3 dataframes merged (1,2,3 see section B), grouped by 'Falls within' and 'First half of postcode'
 
	5. 'sas_agerange_agg_output' - grouped by 'Area' and 'Age range'
 
	6. 'sas_outcome_agg_output' - grouped by 'Area' and 'Outcome'


### D) How processes are separated between Staging, Primary and Reporting layers (see docstrings for specific applications to each dataframe):

	Staging:
		Loads, processes, and outputs data from various CSV datasets, performing the necessary staging 
    		transformations for each dataset. This includes concatenating, renaming columns, and performing
    		other transformations like converting dates and formatting text

	Primary:
		Merges, filters, rounding, splitting columns, replacing specific column values, rounding values are performed, 
		preparing it for reporting.

	Reporting:
		Aggregates and summarizes processed datasets for reporting purposes, generating key insights like crime 
        	counts per area, outcomes, and other indicators.


