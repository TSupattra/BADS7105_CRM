# Customer Segmentation

## Data set : Supermarket data

## Feature
   - Total visits = COUNT(DISTINCT BASKET ID)
   - Ticket size = SUM(SPEND)/COUNT(DISTINCT BASKET ID)
   - Total no. of SKUs
   - Recency = Maxday -Lastdate
   - Totaldays_TotalVisits = Totalday/TotalVisit
   - ToTalQUANTITY_TotalVisits = Total Quantity/Total Visit

## Type of Customer
   ![Customer_seg_0](./Customer_seg_0.jpg)

   by separate to 2 groups
   1. Return customer (Visit more than 1 times)
   2. One visit customer


## Segmentation 1. Return customer (Visit more than 1 times) 
   use kmeans  , n_clusters = 4
   
   ![Customer_seg_1](./Customer_seg_1.jpg)
   

   
   
 
