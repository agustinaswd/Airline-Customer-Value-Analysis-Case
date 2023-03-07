# Airline Customer Value Analysis Case
This is a unsupervised learning project that I got from Bootcamp Data Science at Rakamin Academy.

## Background
Air travel has developed rapidly. With the development of the times, growth in the number of customers is a significant concern considering it will directly impact profit growth. A customer who has used our airline several times feels the service is good and will tend to this service next time. But to get new customers, we must spend a lot on a campaign to attract customers. Most new customers have more to gain than lost old customers. Losing customers is more expensive than acquiring new ones. Old customers can also bring in new customers. Therefore, in this context, airline customer value is analyzed, customers are classified, and the customer loss rate is a top priority. 

## Objective
Develop appropriate marketing modes for different types of customers to maximize profits.

## Research Question
- How is the grouping of customers that we have?
- what should we do to retain our customers?

## Data Analyst
### Data Preprocessing
#### Handling Data Type
- Change 'FFP_DATE', 'FIRST_FLIGHT_DATE', 'LOAD_TIME', 'LAST_FLIGHT_DATE']] = df[['FFP_DATE', 'FIRST_FLIGHT_DATE', 'LOAD_TIME', 'LAST_FLIGHT_DATE' to **datetime**
- Drop missing value

#### Feature Selection
We used LRFMC Model. The colums that will we used are load_time, ffp_date, last_to_end, flight_count, seg_km_sum, avg_discount.<br />
- Loyalty L = LOAD_TIME - FFP_DATE
- Recency R = LAST_TO_END
- Frequency F = FLIGHT_COUNT
- Monetary M = SEG_KM_SUM
- Cabin C = avg_discount

## Modelling using K-Means Clustering
### Elbow Method
![Elbow Method](https://user-images.githubusercontent.com/116469338/223419693-fb30fe93-bde3-42c1-8fd0-56d49f6cbdca.png)
### Silhouette Score
![Silhouette Score](https://user-images.githubusercontent.com/116469338/223420143-244fc333-4599-4694-9dbb-e6c0072cd71a.png)<br />
Evaluation using the elbow method and silhouette score shows that the optimal number of clusters is 4.
### Evaluation with PCA 
![PCA](https://user-images.githubusercontent.com/116469338/223420587-dbb5df53-8fe8-4d8a-bfec-de653fda6e82.png)<br />
From the results above, it can be said that the number of clusters equal to 4 is the correct number of clusters. Where it can be seen that there is a  clear segmentation between the clusters. <br />

## Feature Statistics of Each Cluster
![clusters](https://user-images.githubusercontent.com/116469338/223421343-4da40c0e-8b03-4d18-9037-d5073384026a.png)<br />

## Insight and Recommendation
- Cluster 0: shows customers who have joined for almost seven years, rarely make flights, and the flights are closed **(retained customers)**.
- Cluster 1: shows customers who have joined for almost five years, are active in using airline services, and often travel long distances **(High-value customers)**.
- Cluster 2: shows customers who have joined for about two years (classified as new), often make flights, and are far away **(potential customers)**.
- Cluster 3: shows customers who have joined for about three years (classified as new) but very rarely use flight services and, once used, are also pretty close **(low-value customers)**.

**Business strategy :**<br />
- Create a reward scheme for loyal customers who frequently use flight services. This scheme can increase as expenses made by the customer increase so that these loyal customers feel they have a target to pursue higher reward schemes which, according to them, are profitable and profitable for the company.
- Creating a general promo system (for all customers) in the form of vouchers that have a unique code that the faster it is claimed, the greater the discount value (to lure customers into using flight services more often so that the frequency of using their services increases) and vice versa (the longer it is claimed, the smaller the value of the discount)
