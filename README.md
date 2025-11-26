# 🚖 OLA Data Analyst Project – SQL & Power BI

This project presents a complete analysis of OLA ride-booking data using **SQL** and **Power BI**.  
The goal is to understand ride performance, customer behavior, revenue trends, cancellation patterns, and rating insights.  
The analysis provides actionable information that can help a ride-hailing business optimize its operations.

---

## 📊 Project Overview

This project focuses on:

- Ride volume trends  
- Booking status distribution  
- Revenue contributions by payment methods  
- Customer & driver rating patterns  
- Reasons behind cancellations  
- Vehicle-type performance  
- Top customers by engagement  

The work is divided into two major components:

1. **SQL Analysis** – Querying & extracting insights  
2. **Power BI Dashboard** – Visualization & storytelling  

---

# 🔹 SQL ANALYSIS

## 🛠 Database Structure

The dataset contains key details per booking:

- Booking ID  
- Customer ID  
- Vehicle type  
- Payment method  
- Ride distance  
- Booking status  
- Driver ratings  
- Customer ratings  
- Booking value  
- Incomplete ride flags & reasons  

These fields provide a deep understanding of ride behavior and business KPIs.

---

## 📌 Key SQL Queries

### 1️⃣ Successful Rides  
```sql
SELECT *
FROM bookings
WHERE Booking_Status = 'Success';


2️⃣ Average Ride Distance per Vehicle Type
sql
Copy code
SELECT Vehicle_Type, AVG(Ride_Distance) AS avg_distance
FROM bookings
GROUP BY Vehicle_Type;


3️⃣ Total Customer-Cancelled Rides
sql
Copy code
SELECT COUNT(*) AS total_cancelled_rides
FROM bookings
WHERE Booking_Status = 'Cancelled by Customer';


4️⃣ Top 5 Customers by Ride Count
sql
Copy code
SELECT Customer_ID, COUNT(*) AS total_rides
FROM bookings
GROUP BY Customer_ID
ORDER BY total_rides DESC
LIMIT 5;


5️⃣ Rides Cancelled by Drivers for Personal/Car Issues
sql
Copy code
SELECT COUNT(*) AS cancelled_by_drivers
FROM bookings
WHERE Incomplete_Rides_Reason = 'Personal & Car related issue';


6️⃣ Max & Min Driver Ratings for Prime Sedan
sql
Copy code
SELECT MAX(Driver_Ratings) AS max_rating, 
       MIN(Driver_Ratings) AS min_rating
FROM bookings
WHERE Vehicle_Type = 'Prime Sedan';


7️⃣ Rides Paid via UPI
sql
Copy code
SELECT *
FROM bookings
WHERE Payment_Method = 'UPI';


8️⃣ Average Customer Rating per Vehicle
sql
Copy code
SELECT Vehicle_Type, AVG(Customer_Rating) AS avg_rating
FROM bookings
GROUP BY Vehicle_Type;


9️⃣ Total Revenue from Successful Rides
sql
Copy code
SELECT SUM(Booking_Value) AS total_revenue
FROM bookings
WHERE Booking_Status = 'Success';


🔟 Incomplete Rides with Their Reason
sql
Copy code
SELECT Booking_ID, Incomplete_Rides_Reason
FROM bookings
WHERE Incomplete_Rides = 'Yes';


🔹 POWER BI ANALYSIS
The Power BI dashboard presents an interactive view of the OLA dataset using charts, KPIs, and slicers.

📈 Key Metrics Displayed
⭐ KPIs
Total Sales / Revenue

Average Sales per Ride

Total Number of Rides

Average Customer Rating

📊 Dashboard Sections
1️⃣ Overall Ride Insights
Ride volume over time

Booking success vs cancellations

Daily performance patterns

2️⃣ Vehicle Type Performance
Top vehicle types by ride distance

Rating comparison across vehicle categories

3️⃣ Revenue Insights
Revenue breakdown by payment method

High-value customers

Distance vs revenue relationship

4️⃣ Cancellation Analysis
Customer cancellation reasons

Driver cancellation reasons

Operational improvement areas

5️⃣ Rating Trends
Distribution of driver ratings

Distribution of customer ratings

Detection of mismatches between the two

🔹 Workflow Followed
✔ Data extraction
✔ Data cleaning and transformation
✔ SQL-based analysis
✔ Data modeling in Power BI
✔ DAX calculations
✔ Dashboard creation
✔ Insight generation

