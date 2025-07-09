REAL TIME PARKING PRICING

*   **Overview**

This project implements a real-time **Dynamic Pricing Engine** for smart parking lots using [Pathway](https://pathway.com/). It combines real-time streaming data with analytics and business logic to:

*   Adjust parking prices based on demand (occupancy, traffic, queue, etc.)
*   Apply competitive pricing using geospatial proximity
*   Recommend rerouting to nearby lots when needed

This is a capstone project developed as part of the **IITG Consulting and Analytics** course.

*   **Tech Stack**

Technology - - - -  Purpose

Python Core - - - - Programming language

Pathway - - - - - - Real-time stream processing and dynamic transformations

Pandas - - - - - -  Preprocessing of CSV datasets

Bokeh - - - - - - - Visualization of pricing trends

Google Colab - - -  Development environment

Google Drive- - - - Dataset Hosting

*   **Project Architecture & Workflow**

**1\. Data Ingestion**

*   Read data from Google Drive (CSV)
*   Clean columns and combine date/time fields into a unified timestamp

**2\. Pathway Stream Initialization**

*   Stream created via pw.demo.replay\_csv(...)
*   Data schema includes occupancy, capacity, traffic, queue length, special day flags, etc.

**3\. Model 1: Baseline Pricing**

*   Fixed formula: Price = ₹10 + 5 × Average Occupancy Rate
*   Simple windowed aggregation by day and location

**4\. Model 2: Demand-Based Dynamic Pricing**

*   Weighted demand score:
    *   Occupancy (40%)
    *   Queue Length (20%)
    *   Traffic Condition (20%)
    *   Special Day (10%)
    *   Vehicle Type (10%)
*   Final price: ₹10 + 10 × normalized\_demand

**5\. Visualization**

*   Bokeh line chart showing price fluctuations over time
*   Comparison between baseline and adjusted prices
*   **Additional Documentation**

**Features Considered:**

*   Occupancy vs. Capacity
*   Queue length as a demand indicator
*   Nearby traffic intensity
*   Type of vehicle (car, bike, truck)
*   Special events (e.g. holidays, weekends)

**Why Pathway?**

*   Real-time streaming with low latency
*   Declarative windowing and transformation APIs
*   Plot integration via .plot() and Panel

**Acknowledgements**

*   Project conducted under the IITG **Consulting and Analytics** club.
*   Thanks to the Pathway documentation and mentors for guidance
