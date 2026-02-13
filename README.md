# 🛵 Rapido Ride-Booking Analytics — Power BI

![Data Source](https://img.shields.io/badge/Data_Source-CSV-blue?style=flat&logo=spreadsheet)
![Domain](https://img.shields.io/badge/Domain-Logistics%20%26%20Transport-orange)
![Level](https://img.shields.io/badge/Level-Intermediate-green)
![Tools](https://img.shields.io/badge/Tools-Power_BI-yellow)
![Tools](https://img.shields.io/badge/Tools-DAX-red)

---

## 📌 Project Overview

**Rapido Ride-Booking Analytics** is an end-to-end data analysis project designed to evaluate booking efficiency, revenue generation, and cancellation patterns for a ride-hailing service. The project transforms raw operational data into actionable insights using **Power BI** and **DAX**, replicating real-world logistics performance monitoring.

---

## 🛵 Business Problem

In the highly competitive ride-sharing market, high cancellation rates and inefficient vehicle distribution lead to revenue loss. Rapido needs to identify why rides are being canceled, monitor driver performance, and understand demand patterns across different vehicle types to improve the **"Success Rate."**

---

## 🎯 Business Objectives

- Calculate and monitor the overall **Ride Success Rate**.
- Identify the primary reasons for **Customer and Driver cancellations**.
- Analyze **Revenue contribution** by vehicle category (Bike, Auto, Sedan, SUV).
- Evaluate **Driver and Customer ratings** to ensure service quality.
- Track **Turnaround Time (TAT)** to measure operational efficiency.

---

## 📂 Dataset Information

- **File Name:** `Bookings.csv`
- **Total Records:** 103,024
- **Industry:** Logistics & Transportation (Ride-Hailing)
- **Source:** Synthetic Portfolio Project

---

## 🧾 Dataset Schema

| Column | Description |
| :--- | :--- |
| **Booking_ID** | Unique ID for each ride request |
| **Booking_Status** | Success, Canceled by Driver, Canceled by Customer, etc. |
| **Vehicle_Type** | Type of vehicle (Bike, Auto, Prime Sedan, etc.) |
| **Pickup_Location** | Starting point of the ride |
| **Drop_Location** | Destination point of the ride |
| **V_TAT** | Vehicle Turnaround Time (Arrival time) |
| **C_TAT** | Customer Turnaround Time |
| **Booking_Value** | Total fare/value of the booking |
| **Ride_Distance** | Total distance traveled in km |
| **Driver_Ratings** | Rating given by the customer to the driver |
| **Customer_Rating** | Rating given by the driver to the customer |

---

## 🧪 Key DAX Measures & Analytics

To answer business questions, the following DAX measures were implemented in Power BI:

### 1. Total Booking Volume
```dax
Total Bookings = COUNT('Bookings'[Booking_ID])


### 2. Ride Success Rate

```dax
Successful Bookings = CALCULATE(
    COUNT('Bookings'[Booking_ID]), 
    'Bookings'[Booking_Status] = "Success"
)

Success Rate = DIVIDE([Successful Bookings], [Total Bookings], 0)
```

### 3. Revenue Analysis

```dax
Total Revenue = SUM('Bookings'[Booking_Value])
```

### 4. Cancellation Deep-Dive

```dax
Customer Cancellations = CALCULATE(
    COUNT('Bookings'[Booking_ID]), 
    'Bookings'[Booking_Status] = "Canceled by Customer"
)

Driver Cancellations = CALCULATE(
    COUNT('Bookings'[Booking_ID]), 
    'Bookings'[Booking_Status] = "Canceled by Driver"
)
```

### 5. Average Rating Performance

```dax
Avg Driver Rating = AVERAGE('Bookings'[Driver_Ratings])
```

---

## 📈 Visualizations Included

* **KPI Cards:** Total Bookings, Revenue, Success Rate, and Avg Distance.
* **Booking Status Breakdown:** Donut chart showing Success vs. Cancellations.
* **Vehicle Type Performance:** Bar chart comparing revenue across different categories.
* **Cancellation Reason Tree-Map:** Visualizing why customers and drivers cancel.
* **Location Heatmap:** Identifying high-demand areas in the city.

---

## 💡 Key Insights

* **Success Rate Stability:** A healthy success rate is maintained, but "Driver Not Found" issues peak during specific hours.
* **Cancellation Triggers:** The most common customer cancellation reason is "Driver not moving towards pickup location."
* **Revenue Leaders:** While Bikes have the highest volume, Prime Sedans and SUVs contribute significantly higher revenue per ride.
* **Rating Correlation:** Rides with lower Driver Turnaround Time (V_TAT) consistently receive higher Customer Ratings.

---

## 👨‍💻 Author

**Your Name** – Aspiring Data Analyst

* LinkedIn: https://www.linkedin.com/in/rakesh-kumar-mistri-07ab15334/
* Email: rakeshkumarmistri010413@gmail.com
