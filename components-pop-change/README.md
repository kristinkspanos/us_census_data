# Components of Resident Population Change, 2010 - 2020
The purpose of this project is to clean U.S. Census data and export csv files containing subsets of the data to be used for further analysis.

## Analysis
### 1 - population_change_2010_2020
* Inspects **cbsa-est2020-alldata.csv**
* Calculates cumulative population change for each component from 2010 - 2020
* Exports df that contains all data from **cbsa-est2020-alldata.csv**, plus calculations of cumulative population change for each component, as **popchange_10_20_cumulative.csv**

### 2 - migration_cbsa_data_extract
* Inspects and cleans **popchange_10_20_cumulative.csv** 
  * drops identifer columns that are unnesecary for this analysis
* filters popchange_cumulative by geographic type to only show Metropolitan Statistical Areas and Micropolitan Statistical Areas
  * creates updated 'NAME' column that matches the format of most census datasets, so the file can easily be merged with other datasets in the future
* creates an extract of the df that contains only the identifer columns and cumulative columns
* exports extract as **popchange_10_20_cbsa_slice.csv**

### 3 - migration_county_data_extract
* Inspects and cleans **popchange_10_20_cumulative.csv**
   * drops identifer columns that are unnesecary for this analysis
* filters popchange_cumulative by geographic type to only show counties or county equivalents
* creates an extract of the df that contains only the identifer columns and cumulative columns
* exports extract as **popchange_10_20_county_slice.csv**

## Data Inputs
[Population Estimates and Estimated Components of Resident Population Change For Metropolitan and Micropolitan Areas (cbsa-est2020-alldata.csv)](https://www.census.gov/programs-surveys/popest/technical-documentation/research/evaluation-estimates/2020-evaluation-estimates/2010s-totals-metro-and-micro-statistical-areas.html)

### Identifer Fields
Field | Description
------------ | -------------
CBSA | 
MDIV | 
STCOU |
NAME |
LSAD |

### Numeric Fields
Field | Description
------------ | -------------
CENSUS2010POP | 
ESTIMATESBASE2010|
POPESTIMATE (2010-2020)|
NPOPCHG (2010-2020)|
BIRTHS (2010-2020)|
DEATHS (2010-2020)|
NATURALINC (2010-2020)|
INTERNATIONALMIG (2010-2020)|
DOMESTICMIG (2010-2020)|
NETMIG (2010-2020)|
RESIDUAL (2010-2020)|
