# Real Estate Sales Analysis – Excel Project

This project demonstrates advanced Microsoft Excel skills by analyzing a simulated real estate sales dataset.  
The goal is to build a complete analytics workflow including data cleaning, transformation, and advanced formula analysis.

The project is being developed step-by-step while preparing for the **Microsoft Office Specialist (MOS) Excel Expert certification**.

---

# Dataset

The dataset contains **300 simulated real estate transactions** including:

- Property ID
- City
- Property Type
- Bedrooms / Bathrooms
- Listing Price
- Sale Price
- Days on Market
- Realtor
- Commission Rate
- Commission Earned
- Sale Dates

# Project Structure

excel-real-estate-sales-analysis
│
├── data
│ └── realtor_property_sales_300_records.csv
│
├── excel-workbook
│ └── RealEstate_Sales_Analysis.xlsx
│
└── README.md

# Step 1 – Data Import (Power Query)

The raw dataset was imported into Excel using **Power Query**.

Tasks performed:

- Imported CSV dataset
- Verified data types
- Prepared dataset for transformation
- Loaded data into Excel table format

This step ensures the dataset can be refreshed and reused for analysis.

---

# Step 2 – Data Preparation

The dataset was converted into an **Excel Table** to enable structured references and dynamic formulas.

Table Name:
tbl_sales

Benefits:

- Automatic range expansion
- Structured formula references
- Easier PivotTable creation
- Improved data management

---

# Step 3 – Advanced Excel Formulas

Several calculated columns were added to enrich the dataset and practice advanced Excel functions.

### Price Difference

=[@Sale_Price]-[@Listing_Price]

Measures how much a property sold above or below the listing price.

---

### Price Category

=IF([@Sale_Price]<500000,"Budget",
IF([@Sale_Price]<1000000,"Mid-Range","Luxury"))

Classifies properties into price segments.

---

### Commission Validation

=IFERROR([@Sale_Price]*[@Commission_Rate],0)

Recalculates commission to validate dataset accuracy.

---

### Sale Year


=YEAR([@Sale_Date])

Used for time-based analysis.

---

### Sale Month

=TEXT([@Sale_Date],"mmmm")

Converts the sale date into a readable month format.

---

### End of Month

=EOMONTH([@Sale_Date],0)

Standardizes dates for monthly financial reporting.

---

### Market Demand Indicator

=IF(AND([@Sale_Price]>1000000,[@Days_on_Market]<30),"High Demand","Normal")

Identifies high-value properties that sold quickly.