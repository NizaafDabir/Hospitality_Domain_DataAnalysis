# 🏨 AltiQ Hospitality Analysis
![360_F_286386252_3upNksBL4Pu6KD8Go1i0BpDLCltJyUMr](https://github.com/NizaafDabir/Hospitality_Domain_DataAnalysis/assets/110449627/c6825592-ea8a-4e15-ac65-647477ec1069)
![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
## Introduction
Welcome to the Hospitality Power BI Dashboard repository! This project aims to provide a comprehensive and insightful visualization solution tailored for the hospitality industry. Whether you are a hotel manager, event planner, or hospitality data enthusiast, this Power BI dashboard offers key metrics and analytics to empower better decision-making and enhance operational efficiency.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
## Data Transformation
Abhishek Anand is a Revenue Manager of the Hotel who is our stackholder has provided us the Data. We have firstly loaded this Data in Power BI. Than with the use of power query in Power BI we have Performed Data Preprocessing and Data Cleaning to Transform the data so that it can be used for computing insights from it.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
## Data Modelling

Data Modeling is performed on all the Datasets using Power BI. Datasets are being connected to each other based on the defined primary keys of the Datasets.

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## Data Analysis Expression (DAX)
Created Measures using Data Analysis Expression (DAX) in Power BI. Measures and calculated coloumns created are as follows :

- Revenue: `SUM(fact_bookings[revenue_realized])`
- Total Bookings: `COUNT(fact_bookings[booking_id])`
- Total Capacity: `SUM(fact_aggregated_bookings[capacity])`
- Total Successful Bookings: `SUM(fact_aggregated_bookings[successful_bookings])`
- Occupancy %: `DIVIDE([Total Successful Bookings], [Total Capacity], 0)`
- Average Rating: `AVERAGE(fact_bookings[ratings_given])`
- No of days: `DATEDIFF(MIN(dim_date[date]), MAX(dim_date[date]), DAY) + 1`
- Total Cancelled Bookings: `CALCULATE([Total Bookings], fact_bookings[booking_status]="Cancelled")`
- Cancellation %: `DIVIDE([Total Cancelled Bookings], [Total Bookings])`
- Total Checked Out: `CALCULATE([Total Bookings], fact_bookings[booking_status]="Checked Out")`
- Total No Show Bookings: `CALCULATE([Total Bookings], fact_bookings[booking_status]="No Show")`
- No Show Rate %: `DIVIDE([Total No Show Bookings], [Total Bookings])`
- Booking % by Platform: `DIVIDE([Total Bookings], CALCULATE([Total Bookings], ALL(fact_bookings[booking_platform]))) * 100`
- Booking % by Room Class: `DIVIDE([Total Bookings], CALCULATE([Total Bookings], ALL(dim_rooms[room_class]))) * 100`
- ADR (Average Daily Rate): `DIVIDE([Revenue], [Total Bookings], 0)`
- Realisation %: `1 - ([Cancellation %] + [No Show Rate %])`
- RevPAR (Revenue per Available Room): `DIVIDE([Revenue], [Total Capacity])`
- DBRN (Daily Bookings Rate per No of Days): `DIVIDE([Total Bookings], [No of days])`
- DSRN (Daily Stay Rate per No of Days): `DIVIDE([Total Capacity], [No of days])`
- DURN (Daily Checked Out Rate per No of Days): `DIVIDE([Total Checked Out], [No of days])`
- Revenue WoW Change %: `A week-over-week change for Revenue`
- Occupancy WoW Change %: `A week-over-week change for Occupancy`
- ADR WoW Change %: `A week-over-week change for ADR`
- RevPAR WoW Change %: `A week-over-week change for RevPAR`
- Realisation WoW Change %: `A week-over-week change for Realisation`
- DSRN WoW Change %: `A week-over-week change for DSRN`

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)
## Dashboard

Dashboard is created after creating the DAX measures. For creating this Dashboard Power BI Destop is used.

![Screenshot 2024-01-24 152848](https://github.com/NizaafDabir/Hospitality_Domain_DataAnalysis/assets/110449627/ad5400e9-9fd4-4d79-b027-f62bb89f7456)

![-----------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

## Reference

* Channel Name : codebasics
* Link to the Project : [https://www.youtube.com/watch?v=4QkYy1wANXA](https://www.youtube.com/watch?v=tT4V7zguCnc&t=33s)

[![LinkedIn Badge](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/nizaaf-dabir-524596203/)
[![GitHub Badge](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/NizaafDabir)
