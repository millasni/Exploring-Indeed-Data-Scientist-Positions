# Exploring-Indeed-Data-Scientist-Positions
Exploring data scientist positions on Indeed (as of Sep 5, 2020)

The dataset to be imported (data_05-09-2020.csv) contains Montreal and Toronto based positions collected manually on Indeed.ca on Sep 5, 2020 using 'data scientist' as a search keyword. To obtain salary estimates, in addition to this keyword, I used several filters for annual salary. When a filter is used, the search returns positions with the estimated salary equalling at least the specified amount.

Level 'All' in salary means all positions, whether having estimated salary information or not. 
A filter for 60K will return positions for 60K, 70K, 80K, and so on while that of 70K - positions for 70K, 80K, 90K and so on. 
Due to manual data collection, the same position, depending on its salary, can appear in the untreated data set several times under different salary labels. 

The code will first reshape the data from long to wide format (using 'unstack' command) and then remove duplicate positions, keeping results from the filter with the highest salary for a given position (the last occurrence of the same position in the data set).
There is no guarantee that ALL duplicates are removed - some positions, while being identical, might have been posted, say, 12 and 13 days ago and will appear twice (but this is not widespread; to be improved).  

After these transformations, one line will correspond to one position. Positions with salary not available will still have 'All' in the Salary field (this should be interpreted as NA). 
This reshaped data is available in the file data_reshaped-05-09-2020.csv.

So far, a brief analysis by location/recency/salary/company is available. To be continued...

