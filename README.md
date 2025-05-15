# ConnectingAmerica
Replication Package for Connecting America? Evaluating the Impacts of the Connect America Fund on Broadband and Employment

This directory contains files for replicating the research conducted in Connecting America? Evaluating the Impacts of the Connect America Fund on Broadband and Employment. 

finalDfsLink - google drive link to retrieve final block and tract dataframes. please contact me if it isn't working.
replicate - python methods for replicating data cleaning. In order to run data replication, you will need to download the data from three sources:
  form477:https://www.fcc.gov/general/broadband-deployment-data-fcc-form-477
  caf:https://data.usac.org/publicreports/caf-map/
  acs:https://data.census.gov/

downloading caf data is easy. form 477 data is straightforward, but takes a long time. In addition, some december files are missing / do not download. Download all available years and place in one folder. 
To download the ACS data, search for the following codes. Ensure you select census tract level and check the filter 'all census tracts in the united states'.

download 5 year estimates. Do not download selected profiles. Sometimes the box is automatically checked, make sure to uncheck it. Select all years from 2010 onwards.
ACS COLUMNS: B01003  B02001  B01001  B15003  B23025  B25010  B25003  B19301

Unzip into one folder. This is your acsDir for replicate.

Technically, you also need to download the tigerline shape files from: https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.2020.html#list-tab-790442341
I do not recommend this. You have to query for each state and the download time is atrocious. I only use this to get the total number of tracts and blocks in a county. I provide a df of this as well. if you want to avoid the hassle, you can use this df and put shapeFileIsDir = True when running the replicate method. This will let you skip that part of the data aggregation, and the path will be treated as a final df instead of a directory of state geographies. 

