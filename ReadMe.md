# **SyriaTel Customer Churn**


## Business Problem 
SyriaTel, a leading mobile telecommunication provider, that faces a critical challenge in mitigating customer churn within its subscriber base. The company seeks to address the increasing attrition rates observed among its clientele. Identifying the underlying factors driving customer defection and implementing proactive strategies to retain valuable subscribers are imperative to sustain profitability and competitiveness in the telecommunications industry. Therefore, there is a pressing need to develop robust predictive models and actionable insights to effectively manage and reduce customer churn rates, thereby optimizing customer retention efforts and enhancing overall business performance.



## 1. Business Understanding
The SyriaTel Customer Churn project aims to address a significant real-world problem faced by telecommunications companies worldwide: customer churn. Churn, or the rate at which customers discontinue their services with a company, poses a substantial challenge to the profitability and sustainability of telecom providers. In the case of SyriaTel, the escalating churn rates within its subscriber base underscore the urgency of implementing effective strategies to mitigate attrition and enhance customer retention.

Stakeholders involved in this project include 
* Syriatel Mobile Telecom
* Shareholders
* Employees
* Customers. 

For SyriaTel, reducing churn directly impacts profitability by retaining valuable subscribers and sustaining long-term revenue streams. Moreover, satisfied customers are more inclined to advocate for the company, enhancing its brand image and market reputation. Customers benefit from improved services and reduced churn, experiencing enhanced satisfaction and uninterrupted connectivity.

Project Objectives:

1. Identify key predictors of churn within SyriaTel's subscriber base.
2. Develop proactive retention strategies based on churn indicators.
3. Evaluate the effectiveness of implemented strategies in reducing churn rates.
4. Enhance customer experiences and satisfaction through targeted initiatives.


The SyriaTel Customer Churn project holds significant implications for both the company and its customers. By accurately identifying churn predictors and implementing proactive retention strategies, SyriaTel can effectively mitigate customer churn, optimize satisfaction levels, and maintain a competitive edge in the telecommunications industry. This initiative not only addresses a pressing real-world problem but also empowers stakeholders—from SyriaTel itself to its shareholders, employees, and customers—to benefit from enhanced services, sustained revenue streams, and improved market positioning.



## 2. Data Understanding
The dataset was obtained from Kaggle and it comprises 3333 rows and 21 columns. The dataset for the SyriaTel Customer Churn project comprises several features that provide valuable insights into customer behavior and engagement with SyriaTel's telecommunications services. 

These features include:State, Account_Length, Area_Code, Phone_Number, International_Plan, Voice_Mail_Plan, Number_Vmail_Messages, Total_Day_Minutes, Total_Day_Calls, Total_Day_Charge, Total_Eve_Minutes, Total_Eve_Calls, Total_Eve_Charge, Total_Night_Minutes, Total_Night_Calls, Total_Night_Charge, Total_Intl_Minutes, Total_Intl_Calls, Total_Intl_Charge, Customer_Service_Calls, Churn.

These features provide a comprehensive view of various aspects of customer interaction with SyriaTel's services, including usage patterns, plan subscriptions, and customer service engagement. Analyzing these features will facilitate the identification of key drivers of churn and the development of predictive models to mitigate customer attrition.


## 3. Data Preparation

This analysis included meticulous checks for missing values and duplicates to guarantee data integrity. Feature engineering was employed to create new features potentially relevant to churn prediction, enriching the available data.  Furthermore, phone numbers were established as the index, facilitating efficient customer identification and data manipulation. Outlier detection and multicollinearity analysis were conducted to identify and address any anomalies or redundant features that could negatively impact model performance. Through these comprehensive data preparation steps, a robust and informative dataset was established, ready for further analysis and model development.

## 4. Data Analysis


![Alternative text](https://github.com/idatonui/Phase-3-project-SyriaTel-Customer-Churn/blob/main/images/output%203.png)


![Alternative text](https://github.com/idatonui/Phase-3-project-SyriaTel-Customer-Churn/blob/main/images/output%205.png)



## 5. Modeling
During the analysis, various machine learning models were investigated to predict customer churn for SyriaTel. Each model's performance was evaluated on unseen data to assess its effectiveness in real-world scenarios.

Here's a summary of the findings for each model:

Logistic Regression: This model achieved good accuracy (77%) but showed an imbalance in handling the two customer churn categories (0 and 1). It excelled at correctly identifying and capturing most non-churning customers (class 0) but struggled with precision for churning customers (class 1).

Decision Tree: This model offered similar overall accuracy (80%) but prioritized capturing non-churning customers (high recall) at the expense of misclassifying some churning customers. This might be preferable if it's crucial to retain existing customers, even if it means some false positives (non-churning customers identified as churning).

Random Forest: This model outperformed the previous two with the highest accuracy (92%) and a more balanced approach to both customer churn categories. It achieved high precision for both classes, meaning it accurately identified churning and non-churning customers, but like the Decision Tree, it missed a portion of the churning customers.

XGBoost: Initially, this model achieved perfect accuracy (100%) on the training data, but this raised a potential for overfitting. Overfitting means the model memorized the training data too well and might not perform as well on completely new data.  However, by adjusting model parameters through a technique called Grid Search, we were able to achieve a good balance between training and validation accuracy (99.29% and 95.43% respectively). This suggests the model is less likely to overfit while still performing well on unseen data.

Choosing the best model depends on your specific business priorities. If it's critical to minimize customer churn, the Decision Tree or Random Forest might be a good choice. If overall accuracy and precision for both categories are most important, the Random Forest or XGBoost could be better options.


### 1. Confusion Matrix
![Alternative text](https://github.com/idatonui/Phase-3-project-SyriaTel-Customer-Churn/blob/main/images/output%204.png)


### 2. Model Performance
![Alternative text](https://github.com/idatonui/Phase-3-project-SyriaTel-Customer-Churn/blob/main/images/output%206.png)

### 3. Feature Importance
![Alternative text](https://github.com/idatonui/Phase-3-project-SyriaTel-Customer-Churn/blob/main/images/output.png)


## Conclusion
The XGBoost model was a bit too focused on remembering every detail from the training data (100% training accuracy). This might make it struggle with completely new customers (overfitting).

By adjusting the learning rate and tree complexity, this improves the model. Now it remembers the important things from the training data (99.29% training accuracy) but isn't overloaded with unnecessary details. This should make it perform better on unseen customers (validation accuracy went up to 95.43%).

Tuning the model to be more accurate at predicting customer churn for SyriaTel, even for customers it hasn't seen before. This can help SyriaTel identify customers who are at risk of leaving and take steps to keep them happy.

Additionally, the model identified the most important factors influencing customer churn:

Customers with international plans (International_Plan_yes) are most likely to churn.
A high number of customer service calls (Customer_Service_Calls) suggests dissatisfaction and potential churn.
Customers making many international calls (Total_Intl_Calls) might be unhappy with price or quality.
Fewer voicemail messages (Number_Vmail_Messages) could indicate less engagement and a higher churn risk.
High daytime call usage (Total_Day_Minutes) might signal unmet needs and potential churn.
By focusing on these factors, SyriaTel can develop targeted strategies to reduce customer churn and improve customer satisfaction.


## Recommendation
1. Address International Calling Needs:

Analyze reasons for churn: Conduct surveys or targeted campaigns to understand why customers with international plans are churning. Are they unhappy with price, call quality, or specific destinations?
Targeted promotions: Offer competitive international calling rates or bundles for frequent users.
Improve call quality: Invest in network infrastructure or partnerships to ensure clear and reliable international connections.

2. Enhance Customer Service:

Analyze customer service call data: Identify common pain points and areas for improvement. Train customer service representatives to effectively address these issues.
Reduce call resolution time: Implement efficient processes and empower agents to resolve issues quickly and efficiently.
Proactive outreach: Consider proactively contacting customers who have made multiple customer service calls to understand their concerns and offer solutions.

3. Re-evaluate International Calling Pricing:

Competitive analysis: Benchmark international calling rates against competitors. Identify opportunities to offer more competitive pricing for high-volume users.
Tiered pricing plans: Develop tiered pricing plans catering to different international calling needs (e.g., frequent vs. occasional callers, specific destinations).
Promotional offers: Provide introductory discounts or free trials on international calling plans to attract new users and potentially retain existing ones.

4. Increase Customer Engagement:

Analyze voicemail usage: Investigate why some customers receive fewer voicemails. Are they using alternative communication methods?
Personalized communication: Develop targeted communication strategies based on customer usage patterns.
Loyalty programs: Implement loyalty programs to reward frequent users and incentivize continued engagement with SyriaTel services.

5. Cater to Daytime Callers:

Needs assessment: Identify the specific needs of high daytime callers through surveys or focus groups.
Targeted bundles: Develop bundled packages combining daytime calling minutes with other relevant services (e.g., data, SMS) to fulfill their needs.
Off-peak promotions: Encourage customers to make calls during off-peak hours by offering discounted rates or bonus minutes.

By implementing these recommendations based on the identified key churn factors, SyriaTel can address customer pain points, improve satisfaction, and ultimately reduce customer churn.