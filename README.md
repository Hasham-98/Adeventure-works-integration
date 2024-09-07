# Sales Data Processing

This project involves the extracting and processing of sales data from different sources, including CSV and Excel files. 
The project uses Python, specifically the Pandas library, for data manipulation and transformation.

About Dataset

Sales.csv: Contains sales data with columns such as OrderID, OrderDate, ShipDate, Status, CustomerID, ProductID, etc.
Sales.xlsx: Similar to Sales.csv but in Excel format. It contains the same columns with data types better suited for numeric operations.

## project structure


### 1- Loading Data:

    - Reads data from Sales.csv and Sales.xlsx.
    - Creates DataFrames for each data source.
    - Data Concatenation:
                          . Combines the data from both CSV and Excel sources into a single DataFrame.
                          

### 2- Data Transformation:

    - Cleans and transforms the data, particularly converting string-based numeric values into float.
    - Handles currency and other formatted data to ensure numeric operations can be performed.


### 3- Exploration and Analysis:

    - Displays basic information, including data types and null counts.
    - Provides an overview of the sales data by showing the first few rows.


#### Datatype Transformation

A key part of the project is the transformation of string-based numeric data to actual numeric data types. The function str_to_num is used for this purpose:

    def str_to_num(number):
        try:
            num = float(number)  # Casts data to float
            return num
        except:
            try:
                if "$" in number:
                    number = number.replace('$', '')
                    num = float(number)
                    return num
            except:
                print(number)
                return number


### Output
The script generates an output DataFrame that combines the sales data from both sources into one cohesive dataset. This can be further used for analysis, reporting, or integration into other systems.
