`It refers to the techinique used to prepare raw data into clean organized strucuted fromat suitable for analysis or modelling`
- Improves data quality
- Enhance model performance 
- Reduce Computational complexity
- Ensuring Computability 

## DATA CLEANING 
Data cleaning is used to clean The data by filling in missing values smoothing noisy data Identifying or removing anomaly and resolving inconsistencies If the data is dirty the outcome of the data mining is also unreliable 

### Missing values
- Ignore the tuple 
- Filling in the missing values manually 
- Using a global constant to fill in the missing values
- Use a measure of central tendency for the attribute (`Mean` `median`) to fill in the missing value
- Use the attribute mean or median for all sample belonging to the same class as the given tuple
- Use the most probable value to fill in the value 
### Noisy Data 
`Random error or variance in a measured variable`
- **Binning** Binning is the method of Smoothening a sorted data value by consulting the surrounding values 
	1. Smoothing by bin mean
		- Each values in a bin is replaced by the mean value of the bin
	2. Smoothing by bin Medians
		- Each values in the bin is replaced by the bin median
	3. Smoothing by bin Boundaries
		- The minimum and maximum values in a given bin are identified as the bin boundaries, each bin value is replaced by the closest boundary values
### Regression
**Regression** is a way to make messy or noisy data look clearer by finding the general pattern.

Imagine many dots on a graph scattered around. Regression draws a line or curve through them that best shows the overall direction. This helps ignore random ups and downs.

Regression helps **predict values** and **find trends** from data.

**1. Linear Regression**  
Used when there are **2 variables**.  
It draws a straight line to show how one thing changes with another.

Example:  
Study hours → Exam marks

**2. Multiple Linear Regression**  
Used when there are **more than 2 variables** affecting the result.

Example:  
Exam marks depend on:

- Study hours
- Sleep time
- Attendance
## Outlier Analysis 
 Outliers may be detected by clustering, for 
example, where similar values are organized into groups, or “clusters.” 
Intuitively, values that fall outside the set of clusters may be 
considered outliers


## Major Tasks in data Preprocessing

1. Data Integration
	- This would include integrating multiple databases,data cubes or files 
	- Some of the problems during Data integration are Schema integration object matching
2. Data reduction
	- **Data Reduction** means reducing the size of data while keeping almost the same useful information and results. It makes data easier and faster to analyze.
	- **Dimensionality Reduction**  
		* Reduces the number of columns/attributes/features in data.
			* A student dataset has: Name, Age, Marks, Attendance, Address, Phone.  We may keep only useful columns like Marks and Attendance.
	* **Numerosity Reduction**
		* Reduces the number of rows/records.
			* Instead of storing 10 lakh sales records, keep summary data like monthly totals.
	* Normalization
		* It means scaling data into a small range like **0 to 1**.
			* Salary = 50000 becomes 0.5
3. Data Transformation
	- It involves converting data into a format suitable for analysis
4. Data Normalization: The process of scaling data to a common range to ensure consistency across variables
5. Discretization: Converting continuous data into discrete categories for easier analysis
6. Data Aggregation: Combining multiple data points into a summary form, such as averages or totals, to simplify analysis
7. Concept Hierarchy Generation: Organizing data into a hierarchy of concepts to provide a higher-level view for better understanding and analysis.

## Attribute
An **attribute** is a **property or characteristic** of an object in data.  
It is basically a **column in a table/database**

## 1. Nominal Attribute

Used for **names/categories only**. No order.


## 2. Binary Attribute

A nominal attribute with only **2 values**.

#### Types of Binary:

**Symmetric Binary**  
Both values equally important.  
Example: Gender = Male/Female

**Asymmetric Binary**  
One value more important.  
Example: HIV Test = Positive/Negative


## 3. Ordinal Attribute

Values have **order/rank**, but difference is unknown.Examples:

- Small, Medium, Large
- Poor, Average, Good, Excellent
## 4. Numeric Attribute

Numbers that can be measured.

Examples:

- Age = 20
- Salary = 50000
- Height = 175 cm
### a) Interval-Scaled

Equal gaps, but **no true zero**.

Examples:
20°C is 5°C more than 15°C  
But 20°C is **not twice as hot** as 10°C.

### b) Ratio-Scaled

Has a **true zero**, ratios make sense.
Examples:
20 kg is twice 10 kg.

# Discrete vs Continuous Attributes

## Discrete Attribute

Has separate countable values.

Examples:

- Number of students = 10
- Age = 18, 19, 20
- Smoker = 0 or 1

## Continuous Attribute

Can take any value in a range.

Examples:

- Height = 172.5 cm
- Weight = 65.7 kg
- Temperature = 36.8°C