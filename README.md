# statFin-to-pandas
A Python sequence to search and query Statistics Finland API data.
A stripped forked version of the Stats-to-pandas package by hmelberg.

# Examples

To query the StatFin data, you need to specify with a dictionary containing a user-specified name and the API url to that data. That is:

dataDict = {"some_data_name": "url_to_statfin"}

## Searching Statfin:

To look through the StatFin data, one can use the searchStatfin function, which returns the set of url's that match the search query.

E.g. searchStatfin("input output basic prices") return:


|title |urlDict |published |
|-----|-------|---------|
|004 -- Input-output table at basic prices 2010...|kan/pt/statfin_pt_pxt_004.px|2018-12-05T09:47:00|
|006 -- Input coefficients 2010-2015 (TOL2008/C...|kan/pt/statfin_pt_pxt_006.px|2018-12-05T09:47:00|


## Performing the query:

To get the actual data, use the getData function, which stores the data as a .csv file.

getData(dataDict = {"input-output-tables": "kan/pt/statfin_pt_pxt_004.px"}, outputfolder="rawdata")

If no outputfolder is specified, the data is stored to the working directory. Otherwise, the specified folder will be used (one is generated if that does not already exist).
