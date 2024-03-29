![Market basket](https://github.com/dannieRope/Market_Basket_Analysis_With_Excel/assets/132214828/2f1e5ff0-93bd-4dfe-a459-b37ba4c349c5)


# MARKET BASKET ANALYSIS (ASSOCIATION RULE ANALYSIS)

Market basket analysis is a data mining technique used by retailers to increase sales by better understanding customer purchasing patterns. It involves analyzing large data sets, such as purchase history, to reveal product groupings, as well as products that are likely to be purchased together.
It is one of the key methods used to uncover the hidden strong relational between product combination.

## PURPOSE OF MARKET BASKET ANALYSIS

Finding items that buyers desire to buy is the major goal of market basket analysis. Market basket analysis may help sales and marketing teams develop more effective product placement, pricing, cross-sell, and up-sell tactics.

EXAMPLE - When a customer buys bread, he is likely to also buy butter. Examples of association rules include the following: "Bread" -> "Butter"

1. **Antecedent:**
   - In the context of association rules (e.g., in market basket analysis), the antecedent is the "if" part of the rule. It represents the item or set of items that precede the association. In simpler terms, it's the condition or event that leads to the other item.
   - The entities or "itemsets" produced from the data are called antecedents. To put it another way, it's the IF element on the left. In the situation before, bread serves as the antecedent.

   - **Example:**
     If {A} is the antecedent, the rule could be {A => B}, suggesting that when item A is bought (the antecedent), item B is also likely to be bought.

2. **Consequent:**
   - The consequent is the "then" part of the association rule. It represents the item or set of items that follow the antecedent. In other words, it's the outcome or event that is associated with the antecedent.
   -  It refers to an item or group of items that are encountered along with the antecedent. The THEN part of the sentence is displayed on the right-hand side. The result in the aforementioned case is butter.

   - **Example:**
     If {B} is the consequent, the rule {A => B} suggests that when item A is bought (the antecedent), item B is likely to be bought as well (the consequent).

In summary, in association rules like {A => B}, item A is the antecedent (the condition), and item B is the consequent (the outcome). These rules help identify patterns in data, such as which items are frequently purchased together.


Here's a breakdown of the concepts in the context of association mining:

1. **Support:**
   - Support measures the frequency or occurrence of a specific itemset in the dataset. It is calculated as the number of transactions containing the itemset divided by the total number of transactions.

   - **Formula:**
     Support({A, B}) = {Transactions containing both A and B}/{Total transactions}

2. **Confidence:**
   - Confidence measures the likelihood that a customer who buys item A will also buy item B. It is calculated as the number of transactions containing both A and B divided by the number of transactions containing A.

   - **Formula:**
     Confidence({A => B})) = Support({A, B})/Support({A\})

3. **Lift:**
   - Lift measures how much more likely item B is bought when item A is bought, compared to when item B is bought independently of item A. It helps identify the strength of the association.

   - **Formula:**
    Lift({A=>B}) = Confidence({A=>B})/Support({B})

   - A lift value greater than 1 indicates a positive association. If lift equals 1, the items are independent, and if less than 1, they are negatively associated.

Association rules help businesses understand customer behavior, optimize product placements, and design targeted marketing strategies. 

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# MARKET BASKET ANALYSIS USING THE TITANIC DATASET 

## CASE STUDY 1
The sinking of the Titanic is one of the most infamous shipwrecks in history.
On April 15, 1912, during her maiden voyage, the widely considered “unsinkable” RMS Titanic sank after colliding with an iceberg. Unfortunately, there weren’t enough lifeboats for everyone on board, resulting in the death of 1502 out of 2224 passengers and crew.

While there was some element of luck involved in surviving, it seems some groups of people were more likely to survive than others.
Use the data sheet to identify children, adults, and seniors (Passengers above 50 years of age) under different age groups. Ignore records when incomplete passenger details are available. 

**QUESTION**

- **Using rules of association (Support, Confidence, and lift) determine which cohort of passengers across age group, class travelled in, and gender, had the greatest chance of survival. Using passenger data (i.e name, age, gender, socio-economic class, etc).**


## DATA CLEANING AND PREPARATION

The dataset was obtained from [Kaggle](https://www.kaggle.com/datasets/yasserh/titanic-dataset) and cleaned up using Excel's power query. 
I removed duplicates and null values, checked that the data types were correct, and converted the columns so that the dataset was ready for analysis. You can see the M code for data transformation [here](https://github.com/dannieRope/Market_Basket_Analysis_With_Excel/blob/main/datacleaning.pq).

Below is the image of the data after transformation. 

![Screenshot (457)](https://github.com/dannieRope/Market_Basket_Analysis_With_Excel/assets/132214828/3d986dc8-c864-48a3-842d-576b8982dc37)

## ANALYSIS


**TWO WAY LIFT**

![TWO WAY LIFT](https://github.com/dannieRope/Market_Basket_Analysis_With_Excel/assets/132214828/f6800881-4613-4396-af94-cb75bd1ec4da)

- INSIGHTS
1. Among the factors analyzed, Females exhibit the highest lift value of 1.86, with First Class closely behind at 1.6. This suggests that the Female and First Class category has a greater likelihood of survival compared to other groups.

**THREE WAY LIFT**

![THREE WAY LIFT](https://github.com/dannieRope/Market_Basket_Analysis_With_Excel/assets/132214828/a4b07a53-cee9-4d09-83e8-a17fcfd99355)

- INSIGHTS
1. The combination of First Class and Female passengers stands out with the highest lift of 2.38, followed closely by Second Class and Female with a lift of 2.26. This indicates that Females in First Class have the highest likelihood of survival, followed by Second Class Females.

**FOUR WAY LIFT**

![FOUR WAY LIFT](https://github.com/dannieRope/Market_Basket_Analysis_With_Excel/assets/132214828/da71a24a-497a-4288-8f94-592969c3a188)

- INSIGHTS
1. The combination of First Class, Female, and Adult demonstrates the highest lift value of 2.38, closely followed by the combination of Second Class, Female, and Adult at 2.25. This suggests that Adult females in First Class have the highest likelihood of survival, followed by Second Class adult females.

Find the excel workbook for this analyis [here](https://github.com/dannieRope/Market_Basket_Analysis_With_Excel/blob/main/Titanic.xlsx)

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# MARKET BASKET ANALYSIS USING THE SALES DATA

## CASE STUDY 2
The dataset contains sales transactions for various products, such as vegetables, baby items, fruits, milk, DVDs, and meat, spanning the entire week. The dataset comprises approximately 2928 rows. 

**QUESTION**
- **Utilizing this data, determine the product that is most suitable for cross-selling with vegetables.**

# DATA CLEANING AND PREPARATION 

There are no null values or duplicates in the provided data, and the data types are accurate. It is confirmed that no data cleaning is required after a thorough cross-check.
Below is an image of the dataset

![salesTransaction](https://github.com/dannieRope/Market_Basket_Analysis_With_Excel/assets/132214828/32d121ea-ec1d-407c-bdab-281be5a66e59)


## ANALYSIS 

![Analysis](https://github.com/dannieRope/Market_Basket_Analysis_With_Excel/assets/132214828/68113f90-9e31-4a80-afcc-2842df32650d)

-INSIGHTS

1. Meat exhibits the highest lift value with vegetables, registering a lift value of 1.01. This indicates a robust relationship between meat and vegetables, suggesting that a significant portion of customers purchasing meat also tend to buy vegetables.

Find the excel workbook for this analyis [here](https://github.com/dannieRope/Market_Basket_Analysis_With_Excel/blob/main/Vegetables.xlsx)


# CONCLUSION
- **Case 1**
The results suggest that adult females traveling in First Class had the best chance of surviving the Titanic ship disaster.

- **Case 2**
A significant portion of consumers who purchase meat also purchase vegetables. Cross-selling meat and vegetables together is a smart way to increase vegetable sales.

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
# THANKS FOR READING 


