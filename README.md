## ***Banglore Property Price Analysis--Statistical Masures***  
![image](https://github.com/user-attachments/assets/770703b0-3922-4671-beb5-f8b479ab3a6d)
***Load the dataset***
![image](https://github.com/user-attachments/assets/0d74b088-98e4-4bde-b7e8-dcd66c762876)
## ***Q1. Perform basic EDA***
***Display the first few rows of the dataframe to understand its structure***
![image](https://github.com/user-attachments/assets/3ecabe6d-9e84-4dda-a9ea-ea9a98f7ce14)
![image](https://github.com/user-attachments/assets/b8700d7b-17be-4868-856a-4e93e8ebca9b)
***Dimensions of the DataFrame, which consists of the number of rows and columns***
![image](https://github.com/user-attachments/assets/6c1c59f0-5b6b-4310-87bd-de0158662f2a)
![image](https://github.com/user-attachments/assets/dd45a210-6cfe-4a6f-ba9d-c3e807ae24b0)
***Check data types and non-null counts***
![image](https://github.com/user-attachments/assets/ff5bd3be-98ac-496a-b3a8-2dc51775317f)
![image](https://github.com/user-attachments/assets/2d6534f0-2f3d-4398-80f3-8d6632de451b)
***Check the Missing Values in the dataset***
![image](https://github.com/user-attachments/assets/853e8ad8-74f6-4307-8f02-a49ca90f78bc)
![image](https://github.com/user-attachments/assets/196aac4e-2332-4c38-b9de-13770e94e6c7)
***Display summary statistics***
![image](https://github.com/user-attachments/assets/0e5cf550-fa1c-48f8-b4b0-531ec1d8eec4)
***Check duplicate records in the dataset***
![image](https://github.com/user-attachments/assets/d58727fa-aef6-450e-81c2-f74af9421810)
![image](https://github.com/user-attachments/assets/380a727e-38dd-4fe5-80bc-005a5aeadb38)
***Check the unique records in the dataset*** & ***Remove duplicates***
![image](https://github.com/user-attachments/assets/08ba76dd-38f9-4dcd-87f9-f48625da070d)
***Number of records after deleting the duplicate***
![image](https://github.com/user-attachments/assets/8defe344-09f9-428e-9bc8-b3205586ba73)
***Check dataset is symmetric or assymetric***
![image](https://github.com/user-attachments/assets/740e472d-fc99-490e-a82e-7b2b1a7e9a2f)
![image](https://github.com/user-attachments/assets/64182062-df07-4db8-bea6-939774149212)
***box plot, before the removal of outlier data***
![image](https://github.com/user-attachments/assets/0bd06e67-7eed-4d83-915a-125ddc1339de)
## ***Q2. Detect and Remove Outliers***
***Outliers can affect the analysis significantly .Hence we will used different methods to detect the outliers and opt the best option available***

### ***A).   Mean and Standard Deviation***
![image](https://github.com/user-attachments/assets/918c2443-3994-47a5-9cfc-1da27ac75560)
![image](https://github.com/user-attachments/assets/c6a3eade-0173-4961-853e-6d6777fd82f8)
***Removing Outliers using Standard Deviation Method***
![image](https://github.com/user-attachments/assets/39a8ff0a-9c85-4bfd-b3a5-bf161eced622)
***Outliers Detected and Removed Using Mean and Standard Deviation Method Outliers are detected if they fall outside 
the range of (mean ± 3 * std_dev)***

***Number of outliers detected: 5 Shape of dataset after removing outliers: 12,146 rows and 7 columns***
### ***B). Percentile Method***
***Calculate the lower bound using the 5th percentile***
![image](https://github.com/user-attachments/assets/1ac979af-a5be-4970-add8-cd46ff1605c7)
***Calculate the upper bound using the 95th percentile***
![image](https://github.com/user-attachments/assets/84a62674-522d-414c-9ae2-4dd22aa4a4ae)
***Filter the DataFrame to remove outliers based on the calculated bounds***
![image](https://github.com/user-attachments/assets/80787fb2-e953-4cb6-b89f-4a266c12b97b)
***5th Percentile (lower_bound)Values below this threshold are considered as lower outliers. 95th Percentile (upper_bound)Values above this threshold are considered as upper outliers*** 

***The filtered dataset percentile_newdata retains only the values within this range, effectively removing outliers. 10928 rows x 7 columns***
### ***C). IQR -Interquartile Range Method***
![image](https://github.com/user-attachments/assets/afcd166a-0be0-4c5d-b99f-689de9f41cfe)
![image](https://github.com/user-attachments/assets/c1aded58-a5b0-4b62-bc9e-fcfdb1557775)
***Filter the DataFrame to remove outliers based on the calculated bounds***
![image](https://github.com/user-attachments/assets/c4876d12-20a2-407a-adf7-d7d388c9da72)
***Outliers are detected if they fall above Q1 - 1.5 * IQR or above Q3 + 1.5 * IQR.***

***Q1 = data['price_per_sqft'].quantile(0.25):*** 

***This calculates the first quartile (25th percentile) of the price_per_sqft column***

***Q3 = data['price_per_sqft'].quantile(0.75):***

***This calculates the third quartile (75th percentile) of the price_per_sqft column*** 

***IQR = Q3 - Q1:***

***The IQR is the range between the 25th and 75th percentiles. It measures the spread of the middle 50% of the data***

***Filter the Data to Remove Outliers after 11009 rows x 7 columns***
### ***D). Z-Score Method***
![image](https://github.com/user-attachments/assets/91677151-ccf3-4d06-b00c-f18a439fe3a0)
![image](https://github.com/user-attachments/assets/55002d52-4e3b-4491-addd-6d9c2d76ea60)
## ***Q3. Box Plot Analysis to determine the best outlier removal method***
![image](https://github.com/user-attachments/assets/e026ee10-91ea-4810-b4cc-3a3329c9cbe2)
![image](https://github.com/user-attachments/assets/fe6aa5ef-e7d3-4b68-97fb-16c14eb2da9b)
![image](https://github.com/user-attachments/assets/a1c7a707-39eb-40d4-8349-a5abee36e478)
***A. Mean and Standard Deviation Method:***  
***Effective For: Normally distributed data. Sensitive To: Extreme outliers.***
***Approach: This method identifies outliers based on how many standard deviations a value is from the mean.***

***B. Percentile Method:***  
***Effective For: Data with extreme outliers.
Approach: This method trims a certain percentage (e.g., the extreme 5%) from both ends of the dataset.***

***C. IQR Method:***     
***Effective For: Skewed data and data with extreme outliers.
Approach: This method removes values that lie beyond 1.5 times the Interquartile Range (IQR) from the first and third quartiles. Suitable for skewed distributions. May not be as effective if the data is normally distributed***

***D. Z-Score Method:***  
***Effective For: Normally distributed data. Approach: This method keeps data points with z-scores between -3 and 3, effectively removing those with extreme z-scores.***

***The IQR Method and Percentile Method are more robust and effective for skewed distributions or data with extreme outliers. The IQR Method is particularly beneficial for datasets where the distribution is skewed, as it focuses on the middle 50% of data and removes outliers based on the spread of the middle range. The Percentile Method is highly effective in removing extreme outliers by trimming a specified percentage from both ends, making it useful for datasets with extreme values.***

## ***Q 4.Draw histplot to check the normality of the column(price per sqft column) and perform transformations if needed. Check the skewness and kurtosis before and after the transformation.***
![image](https://github.com/user-attachments/assets/2bb97361-312b-426e-b76c-60fe9543d216)
![image](https://github.com/user-attachments/assets/f250e41e-1943-4e62-9293-172681ff2d28)
![image](https://github.com/user-attachments/assets/88123cde-3e3c-4698-9173-d71d64e56b3c)
***Applying log transformation method to 'price_per_sqrft'***
![image](https://github.com/user-attachments/assets/b33cf20a-d3da-4ac7-a43e-5dbfd61a0935)
***Applying log transformation method***
![image](https://github.com/user-attachments/assets/06b0044a-eaf0-485b-a161-78a7f0d129b2)
![image](https://github.com/user-attachments/assets/a144acd3-7c92-4632-9a23-942fafb18590)
![image](https://github.com/user-attachments/assets/35b8f826-ba1f-4c28-b750-1b9b94505ec2)
***The original price_per_sqft data had a highly right-skewed distribution with a skewness of approximately 103.889 and a very high kurtosis value of around 11131.23, indicating extremely heavy tails.The histogram shows that the data is extremely right-skewed, with a long tail on the right side, which aligns with our skewness and kurtosis values. Through this analysis, we observed that the original price_per_sqft data was highly skewed with extremely heavy tails, as indicated by the very high skewness and kurtosis values*** 

***There are several transformations we can apply to reduce skewness and kurtosis in our data***

***a).   Log Transformation:***  

***Apply the natural logarithm to our data. This works well for data that is strictly positive***  

***Applying a log transformation significantly improved the distribution, resulting in skewness and kurtosis values closer to those of a normal distribution. Transformed Skewness: 1.400238670119574 Transformed Kurtosis: 9.40102516314437 With a transformed skewness of approximately 1.4002 and a transformed kurtosis of around 9.4010, you likely have a distribution that is positively skewed (since the skewness is positive) and leptokurtic (since the kurtosis is greater than 3, indicating heavier tails than a normal distribution)***

***squre root method***
![image](https://github.com/user-attachments/assets/ec249286-72c6-4275-b41b-bf83ccc64beb)
![image](https://github.com/user-attachments/assets/9e06260d-3e01-47a8-b6c9-e07ad612c5a8)
![image](https://github.com/user-attachments/assets/60b7f880-782a-49c6-a937-c146e172690d)
![image](https://github.com/user-attachments/assets/9b1c1100-4235-40ad-bf62-c6e589c8a686)
![image](https://github.com/user-attachments/assets/86e19412-1bc6-43ca-a326-f4f18b9fdce4)
![image](https://github.com/user-attachments/assets/275728aa-598c-4dd3-896d-038ffd8d5150)
![image](https://github.com/user-attachments/assets/0906d9cb-0b30-4720-8c2e-3ca3bd229d8e)
![image](https://github.com/user-attachments/assets/ebe36d50-1bd9-4a15-b6e1-058f8e9c015a)
### ***Q5. Check the correlation between all the numerical columns and plot heatmap***
![image](https://github.com/user-attachments/assets/18a4f4c3-0d54-4a46-b688-643bfaf895dc)
![image](https://github.com/user-attachments/assets/2778f6fc-b130-4e09-8e16-3c90d7df14ff)
***Correlation Heat Map for all the  columns***
![image](https://github.com/user-attachments/assets/ef79bc1a-71cb-4d82-b7ab-00d01e0f8da7)
***Correlation Heat Map without z-score ***
![image](https://github.com/user-attachments/assets/4b78a86c-6075-48d2-a342-844c3b207583)
![image](https://github.com/user-attachments/assets/edc16e44-6deb-440a-b110-0d1f6492371d)
***The correlation coefficient ranges from -1 to 1. 1 indicates a perfect positive linear relationship. -1 indicates a perfect negative linear relationship. 0 indicates no linear relationship.***  

#### ***Key Observations from the Heatmap:***

***Strong Positive Correlation:***

***Bath and BHK (0.9): A high correlation between the number of bathrooms and bedrooms implies that properties with more bedrooms tend to have more bathrooms.***

***Moderate Positive Correlation:***

***Total Square Feet and Price (0.57): This shows that larger properties generally have higher prices.***

***Weak Correlation:***

***Price per Square Foot: This variable has very weak correlations with other variables, suggesting that the price per square foot is relatively independent of other factors in the dataset, such as location-specific amenities or market conditions.***

### ***Insights and Potential Predictors:***


***Total Square Feet, Number of Bathrooms, and Number of Bedrooms are strong predictors of property price.***

***Price per Square Foot is relatively independent, indicating other factors might play a significant role in determining it.***
## ***Q6: Draw Scatter Plot Between Variables to Check Correlation***
![image](https://github.com/user-attachments/assets/7db03ab8-303c-4004-9d68-9feec29c6be0)
![image](https://github.com/user-attachments/assets/70e77790-cbd2-4e10-bbcb-615607704904)
![image](https://github.com/user-attachments/assets/38efa413-29a1-4df1-862f-d919fe312d75)
![image](https://github.com/user-attachments/assets/57c09be3-a3c5-4f50-8379-e881f7b6c402)
![image](https://github.com/user-attachments/assets/6f14451b-8a57-4e1f-8e78-646a08acf4f1)
![image](https://github.com/user-attachments/assets/71a24998-94c9-4167-af8b-e0fbb85cca44)
![image](https://github.com/user-attachments/assets/0726f1a0-ac19-4a43-bef5-e40f162a6058)
![image](https://github.com/user-attachments/assets/49824a5c-6357-4f34-b695-1e39eeb155e0)
![image](https://github.com/user-attachments/assets/5d85e223-29ec-4ad8-8fd3-5254e25d86ba)
![image](https://github.com/user-attachments/assets/7b34d222-2b9d-4d5e-bc07-14a29d0aa805)
![image](https://github.com/user-attachments/assets/049574f6-73a6-477d-98a3-99955db157a6)
![image](https://github.com/user-attachments/assets/13a659f7-59a6-49e1-9b2d-14e5699ac79e)
![image](https://github.com/user-attachments/assets/29bc6bd3-06ef-4303-bfa4-6cf88cd2f218)
![image](https://github.com/user-attachments/assets/90987830-359e-40bc-a2ec-505d3602be9b)
![image](https://github.com/user-attachments/assets/775f21fb-5882-4c26-b95a-885f57e9467c)
![image](https://github.com/user-attachments/assets/2b6f0c55-2352-47ff-b7cd-90c0a3b55bdb)
![image](https://github.com/user-attachments/assets/37859a7b-20ce-4b5b-b2b6-31c951172a2b)
![image](https://github.com/user-attachments/assets/4831e598-960e-418d-b326-1492dc22f015)
![image](https://github.com/user-attachments/assets/7f94424d-aaab-4295-856f-7848ddbb15a3)
![image](https://github.com/user-attachments/assets/a5e8c6dc-c06e-4175-8905-9cf5d0305feb)
![image](https://github.com/user-attachments/assets/31e9515b-4394-419c-9eaf-96946b6fa84f)
![image](https://github.com/user-attachments/assets/02bb7d5e-edde-4527-8ffb-45b4fda6c9f5)
![image](https://github.com/user-attachments/assets/f9597fa7-33ee-4f3a-8753-1c0b2565e9fb)
![image](https://github.com/user-attachments/assets/2b19ce6a-0d7e-4f7a-bdde-aaf9dbd2f340)
![image](https://github.com/user-attachments/assets/ab6384fb-16c5-4f12-b8d0-17cd980ab433)
![image](https://github.com/user-attachments/assets/a3d657ad-4e2a-4323-afbb-e26e26eb25c8)




***The scatter plot matrix provides an extensive visual representation of the relationships among various property features. Key insights include several important correlations:***

***Strong Correlation: There is a strong positive correlation between total square footage and price, indicating that larger properties tend to be more expensive. This relationship aligns with expectations, as larger spaces typically provide more living area and command higher prices.***

***Positive Correlation Between Bedrooms and Price: The scatter plot also reveals a positive correlation between the number of bedrooms and price. Properties with more bedrooms generally have higher prices, which is consistent with market trends.***

***Strong Positive Correlation Between Bathrooms and Bedrooms: There is a strong positive correlation between the number of bathrooms and the number of bedrooms. This suggests that properties often come equipped with multiple bathrooms to complement the number of bedrooms.***

***Moderate Positive Correlation: There is also a moderate positive correlation between total square footage and the number of bedrooms, indicating that larger homes tend to have more bedrooms.***

***Weak Correlation for Price per Square Foot: In contrast, the price per square foot shows only weak correlations with variables such as total square footage, the number of bathrooms, and the number of bedrooms. This suggests that other factors beyond these properties features play a significant role in determining price per square foot.***

***These observations provide valuable insights into property valuations and the key factors influencing real estate pricing.***


