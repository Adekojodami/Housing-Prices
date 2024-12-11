## INTRODUCTION

**BACKGROUND HISTORY**

The Residential Housing Prices Dataset is a critical aspect for buyers, sellers, real estate developers, and policymakers. Housing prices are influenced by various factors, including location, property size, amenities, and market demand. This dataset provides detailed information on residential properties, including features such as the size of the property (area), the number of bedrooms and bathrooms, the presence of amenities (like air conditioning and parking), and the type of furnishings.

## SIGNIFICANCE OF HOUSING PRICES ANALYSIS:
1.	Market Trends: Identifying trends in property prices helps stakeholders make informed decisions about buying or selling homes.
   
2.	Investment Decisions: By analyzing the relationship between property features and prices, investors can identify high-value or undervalued properties.
   
3.	Urban Planning: Insights from housing price data can aid policymakers in urban development and planning, ensuring a balanced real estate market.

## PROBLEM STATEMENT

The major challenges that TDI Properties Development Company are facing in housing price analysis are:

1.	Non-Standardized Data: Variations in data formats, such as inconsistent units for area (e.g., square feet, meters), can complicate analysis.
   
2.	Influence of External Factors: Economic conditions, location-specific factors, and government regulations can introduce variability in housing prices.
   
3.	Feature Importance: Determining which factors (e.g., number of bedrooms, parking availability) significantly influence property prices is often complex.
   
## OBJECTIVES:

The aims of the research works are to uncover the key determinants of residential housing property prices. The insights of the analysis will support how various features of residential properties influence their pricing, and how different property segments can be targeted to optimize pricing strategies. 
 



## DATA DESCRIPTION
**-DATA SOURCE:** 
The was gotten from kaggle.com and focus in housing.

**-Data collection:** 
The data was an excel.csv file and was imported into Structured Query Language (SQL).

**Data Characteristics:**

**Description:**
The datasets consist of 13 columns and 545 rows. It also contains various features of residential properties along with their corresponding prices. It is suitable for exploring and analyzing factors influencing housing prices and for building predictive models to estimate the price of a property based on its attributes.

**Feature	Description**

Price	The price of the property.

Area	The total area of the property in square feet.

Bedrooms	The number of bedrooms in the property.

Bathrooms	The number of bathrooms in the property.

Stories	The number of stories (floors) in the property.

Mainroad	Indicates whether the property is located on a main road (binary: yes/no).

Guestroom	Indicates whether the property has a guest room (binary: yes/no).

Basement	Indicates whether the property has a basement (binary: yes/no).

Hotwaterheating	Indicates whether the property has hot water heating (binary: yes/no).

Airconditioning	Indicates whether the property has air conditioning (binary: yes/no).

Parking	The number of parking spaces available with the property.

Prefarea	Indicates whether the property is in a preferred area (binary: yes/no).

Furnishingstatus	The furnishing status of the property (e.g., furnished, semi-furnished, unfurnished).
	

## METHODOLOGY
**Data Cleaning:**
Data cleaning was done on the datasets, whereby missing values was replaced with NA. The duplicates values were removed and required SQL functions, joins, aggregate functions, or conditional logic are used.

To perform data cleaning and preparation of the housing prices datasets in SQL, follow these steps:

**1. Import the Dataset**

•	Step 1: Open SQL and connect it to server.

•	Step 2: Right click on Database and click on New Database.

•	Step 3: Name your New Database then refresh.

•	Step 4: Then on your Name Database right click on Task and import your dataset

•	Step 5:  Click on New Query “SELECT * FROM HOUSING_PRICE_DATA$”.
 
**2. Create the table.**
CREATE TABLE HOUSE_PRICES (

	price INT PRIMARY KEY,

	stories INT,

	furnishingstatus VARCHAR (50)

	);
	INSERT INTO HOUSING_PRICE_DATA$(price,stories,furnishingstatus)

	SELECT

	price,

	stories,

	furnishingstatus

FROM HOUSING_PRICE_DATA$

SELECT * FROM FURNISHED$

price		stories   	furnishingstatus

13300000	3		furnished

12250000	4		furnished

12250000	2		semi-furnished

12215000	2		furnished

11410000	2		furnished
   
Messages 

(545 rows affected)

Completion time: 2024-11-30T14:26:53.3593944+01:00

**-Statistical Analysis:** Microsoft SQL server management studio is the statistical tools used for analysis


## ANALYSIS
**ANALYSIS QUESTIONS:** 

**1. Find the total price, average price and total number of housing properties.**
SELECT SUM(price) AS [Total Price]

FROM HOUSINGPRICE

Total Price

2597867440
   
SELECT CAST (AVG(price) AS decimal(10,2))  AS [Average Price]

FROM HOUSINGPRICE

Average Price

4766729.25
   
SELECT COUNT(area) AS [TOTAL PROPERTIES]

FROM HOUSINGPRICE

TOTAL PROPERTIES

**2.  WHAT IS THE PRICE OF FURNISHING STATUS--**
   
SELECT furnishingstatus, SUM(price) AS [TOTAL PRICE]

FROM HOUSINGPRICE

GROUP BY furnishingstatus

ORDER BY SUM(price)

furnishingstatus	TOTAL PRICE

unfurnished		    714462000

furnished		      769397440

semi-furnished		1114008000

**3. WHAT IS THE TOTAL NUMBER OF STORIES BUILDING--**
   
SELECT stories, COUNT(area) AS [Total Stories]

FROM HOUSINGPRICE

WHERE stories='1' OR stories='2' OR stories='3' OR stories ='4'

GROUP BY stories

ORDER BY COUNT(area) DESC

STORIES	TOTAL STORIES

       2		238
   
       1		227
   
       4		41
   
       3		39

**4. WHAT IS PRICE OF AREA WITH PARKING--**

SELECT parking, SUM(area) AS [TOTAL AREA] FROM HOUSINGPRICE

GROUP BY parking

ORDER BY SUM(price)

PARKING	  TOTAL AREA

     3		  86140
   
     2		  672449
   
     1		  702621
   
     0		  1345835

**5. HOW MANY HOUSINGS PROPERTY IS CLOSE TO THE MAINROAD--**
   
SELECT	mainroad, count(price) AS [Total Price]

FROM HOUSINGPRICE

WHERE mainroad ='no' OR mainroad ='yes'

GROUP BY mainroad

ORDER BY count(price) DESC

MAINROAD	TOTAL PRICE

    yes		468
   
    no		77



## RESULTS
**Results from the Housing Data Analysis**
The results of the analysis provide insights into how various features of residential properties influence their pricing, and how different property segments can be targeted to optimize pricing strategies. Below are the key results based on the dataset provided:

**1. Price Distribution by Key Features**

Area and Price Correlation:

From the findings area with larger properties (measured in square feet) tend to have a higher price. For instance, properties with larger square footage, such as those with 8,000 sq ft or more, are priced significantly higher. While smaller properties, typically under 5,000 sq ft, are priced lower, indicating the value placed on more space.
 

**2. Furnishing Status and Its Impact on Price**

•Furnishing and Price:
Furnished properties are priced higher compared to semi-furnished or unfurnished properties. This indicates a market preference for ready-to-move-in homes. 

Properties labeled as "furnished" have an average higher price point, suggesting that buyers are willing to pay more for the convenience of furnished homes.

Semi-furnished properties also maintain a relatively higher price than unfurnished ones, but not as high as fully furnished properties.
 
**3. Amenities Impacting Pricing**
   
•	Parking: Properties with more parking spaces (especially two or more) tend to have higher prices. This is particularly true in urban or suburban settings where parking is a premium.

•	Basement: Hence, properties with basements tend to command higher prices, indicating that additional living or storage space adds value to the property.
 
 


**4. Location and Other Key Features**
   
Proximity to Main Road:

•	Properties near or on the main road have higher prices, reflecting the demand for accessibility and visibility in prime areas. However, properties farther from main roads (with fewer amenities) are generally priced lower. That is, 86% of the customers where able to purchases properties to main road while the remaining 14% cannot purchase it.

•	Larger area and more stories strongly influence price. The two (2) stories building was purchased most at the sum of $1,133,849,500 followed by one (1) story building which is $946,739,500, while three (3) and four (4) stories building are purchased which were $221,732,00 and $295,546,440 in the area.

 
 




## DISCUSSION
**INTERPRETATION OF RESULTS**
 


From the above dashboard we can deduce that the total numbers of properties purchases are 545 and the total price amount is $2,597,867,440. Hence, properties area with 6,000 ft.sq was sold most at the price of $169,235,500. Semi-furnished properties were purchased most at the price of $1,114,008,000 while furnished and unfurnished price were sold at $769,397,440 and $714,462,000 respectively. 

The two (2) stories building was purchased most at the sum of $1,133,849,500 followed by one (1) story building which is $946,739,500, while three (3) and four (4) stories building are purchased which were $221,732,00 and $295,546,440 in the area.

However, 191 properties with basement were purchased, 172 properties with air conditioning were also purchased. About 128 0f the customers have their preferred-area and 468 of the customers liked properties close to main-road.





## CONCLUSION

•	The area of the property, number of bedrooms, and furnishing status are the most influential factors determining property prices in the dataset. That is, area with 6,000 ft.sq was sold most at the price of $169,235,500.

•	Luxury features, such as air conditioning, basements, and parking availability, play a critical role in increasing the property value. Particularly properties the urban center.

•	Proximity to main roads and property amenities, such as guest rooms and hot water heating, also drive higher prices, especially in properties located in well-connected or more desirable locations.

By focusing on these key factors, stakeholders in the housing market (such as real estate agents, developers, and buyers) can make better-informed decisions about property valuations, pricing strategies, and potential investment opportunities.



## RECOMMENDATION

•	Target High-Demand Segments: Optimize pricing for semi-furnished properties in high-demand areas. Focus on promoting properties with features like air conditioning, guest rooms, and proximity to main roads, as these are key drivers of higher prices.

•	Develop Pricing Models: Use insights from the analysis to create a standardized pricing model based on features such as area, furnishing status, and luxury amenities. By implementing dynamic pricing strategies for properties in high-demand regions.

•	Enhance Property Features: Consider upgrading older or less expensive properties with modern amenities such as air conditioning, basements, and additional parking spaces to increase their market value.

