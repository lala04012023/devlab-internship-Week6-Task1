# devlab-internship-Week6-Task1
# E-commerce Conversion Analysis

## Project Overview

This project analyzes user behavior and conversion performance in an e-commerce platform. The main goal is to understand how users move through the purchase funnel, identify strong and weak-performing categories and brands, compare monthly conversion performance, and detect potential business opportunities.

The analysis focuses on the following user journey:

**View → Cart → Purchase**

By analyzing this funnel, the project identifies where users are most likely to drop off and which products, categories, and brands are most effective at converting traffic into purchases.

---

## Project Objectives

The main objectives of this analysis are to:

* Analyze the overall conversion funnel.
* Calculate view-to-cart and view-to-purchase conversion rates.
* Compare conversion performance between January and February.
* Identify high-performing and low-performing product categories.
* Analyze brand performance based on purchase volume and conversion efficiency.
* Identify products with high views but low conversion.
* Calculate the average time between product view and purchase for converted users.
* Detect unusual product prices using the IQR method.
* Create visualizations to communicate the main findings.
* Provide actionable business recommendations based on the analysis.

---

## Dataset
https://www.kaggle.com/datasets/mkechinov/ecommerce-events-history-in-cosmetics-shop

The dataset contains e-commerce user interaction events.

The main event types used in the analysis are:

* `view` — a user viewed a product.
* `cart` — a user added a product to the shopping cart.
* `purchase` — a user purchased a product.

Additional information such as product category, brand, price, user, and event timestamp was used to perform more detailed analysis.

---

## Data Preparation

Before performing the analysis, the dataset was inspected and prepared.

The main preparation steps included:

* Loading the dataset.
* Inspecting the dataset structure and data types.
* Checking for missing values.
* Converting date/time columns into an appropriate datetime format.
* Checking unique event types.
* Separating `view`, `cart`, and `purchase` events.
* Grouping data by category, brand, product, and month.
* Preparing data for funnel and conversion calculations.
* Detecting price outliers using the IQR method.

The cleaned data was then used for further exploratory and conversion analysis.

---

# Conversion Funnel Analysis

The main user journey was analyzed using a three-stage funnel:

**View → Cart → Purchase**

The funnel shows how many users reach each stage and how effectively users move from one stage to the next.

### View-to-Cart Conversion

This metric represents the percentage of users who viewed a product and subsequently added a product to their cart.

### View-to-Purchase Conversion

This metric represents the percentage of users who viewed a product and subsequently completed a purchase.

View-to-purchase conversion was treated as one of the main performance indicators because it directly measures how effectively product traffic is converted into sales.

---

# Monthly Conversion Analysis

Conversion performance was compared between January and February.

### Results

| Month    | View-to-Purchase Conversion |
| -------- | --------------------------: |
| January  |                       7.09% |
| February |                       6.79% |

February's conversion rate decreased by approximately **0.30 percentage points** compared with January.

Although the decrease is relatively small, it may indicate changes in user behavior, product availability, pricing, promotions, or the overall shopping experience.

Further investigation is recommended to determine which categories, brands, or products contributed most to the decline.

---

# Category Performance Analysis

Conversion rates were analyzed across product categories to identify which categories perform particularly well and which ones experience significant funnel drop-offs.

## High-Performing Category: `apparel.glove`

The `apparel.glove` category achieved a **38.91% view-to-purchase conversion rate**.

This indicates that users who view products in this category are highly likely to complete a purchase.

The strong performance may be related to factors such as:

* Competitive pricing
* Attractive products
* Effective promotions
* Strong product presentation
* High customer demand

### Recommendation

The product, pricing, and promotional strategies used in this category should be investigated to identify successful practices that could potentially be applied to other categories.

---

## Low-Performing Category: `accessories.bag`

The `accessories.bag` category showed significantly weaker funnel performance:

* **View-to-Cart Conversion:** 4.64%
* **View-to-Purchase Conversion:** 1.43%

The low view-to-cart conversion suggests that many users leave the funnel before showing strong purchase intent.

Possible reasons include:

* High product prices
* Poor product images
* Insufficient product information
* Stock availability problems
* Weak promotions
* Delivery conditions
* Poor product page experience

### Recommendation

The product pages, pricing, stock availability, images, descriptions, and promotional strategy of this category should be reviewed.

---

# Brand Performance Analysis

Brand performance was evaluated using both purchase volume and conversion efficiency.

The analysis shows that the brand with the highest number of purchases is not necessarily the brand with the highest conversion rate.

For example:

* `runail` generated **45,274 purchase events**, making it the brand with the highest purchase volume.
* `bpw.style` achieved a **22.95% view-to-purchase conversion rate**, showing stronger traffic-to-purchase efficiency.

This difference highlights the importance of evaluating brands using more than just total sales volume.

### Business Perspective

A brand can generate a large number of purchases simply because it receives a large amount of traffic.

Another brand may receive less traffic but convert a much larger percentage of its visitors into customers.

Therefore, brand performance should be evaluated using both:

**Purchase Volume + Conversion Efficiency**

---

# High-View, Low-Conversion Products

Products with many views but relatively low purchase conversion were also analyzed.

These products are particularly important from a business perspective because they already attract user attention but fail to convert that attention into sales.

Potential reasons include:

* High prices
* Weak product descriptions
* Poor-quality images
* Low customer ratings
* Limited product information
* Stock problems
* Expensive delivery
* Weak promotional offers
* Strong competition from alternative products

### Business Opportunity

Improving the conversion rate of high-traffic, low-conversion products can potentially increase sales without requiring additional traffic acquisition.

These products should therefore be prioritized for:

* Price optimization
* Product page improvements
* Better images and descriptions
* Promotion testing
* Stock checks
* Customer review analysis

---

# View-to-Purchase Time Analysis

For users who completed a purchase, the time between the initial product view and purchase was analyzed.

This analysis helps understand how quickly users make purchasing decisions.

The timestamps were converted into datetime format, and the difference between the relevant view and purchase events was calculated.

This metric can help the business understand whether customers tend to make immediate purchase decisions or require more time before completing a transaction.

Understanding this behavior can also support decisions related to:

* Retargeting campaigns
* Promotional timing
* Personalized recommendations
* Reminder notifications
* Discount strategies

---

# Price Outlier Analysis

Product prices were analyzed using the **Interquartile Range (IQR)** method to identify unusually high or low values.

Approximately **6.91% of purchase prices** were identified as outliers.

The upper outlier threshold was approximately:

**11.515**

Prices above this value may represent:

* Premium products
* Expensive product categories
* Different product segments
* Incorrectly entered prices
* Potential data quality issues

### Recommendation

These values should not automatically be removed.

Instead, they should be investigated at the product and category levels to determine whether they represent legitimate premium products or potential data errors.

---

# Key Business Insights

## 1. Overall Conversion Has Declined

January's view-to-purchase conversion rate was **7.09%**, while February's rate decreased to **6.79%**.

This represents an approximately **0.30 percentage point decline**.

The decrease suggests that user behavior or product performance may have changed between the two months.

### Recommendation

Investigate which categories, brands, and products experienced the largest conversion declines in February. Pricing, promotions, stock availability, and user experience should also be reviewed.

---

## 2. `apparel.glove` Is a Strong-Performing Category

The `apparel.glove` category achieved a **38.91% view-to-purchase conversion rate**.

This indicates strong purchase intent and effective conversion within this category.

### Recommendation

Analyze the product selection, pricing, promotions, and product presentation of this category and identify successful practices that can be applied to weaker-performing categories.

---

## 3. `accessories.bag` Shows a Significant Funnel Problem

The `accessories.bag` category achieved:

* **4.64% view-to-cart conversion**
* **1.43% view-to-purchase conversion**

This indicates substantial user drop-off during the purchasing funnel.

### Recommendation

Review product pages, prices, stock availability, images, descriptions, promotions, and delivery conditions to identify the main reasons for the low conversion.

---

## 4. The Most Purchased Brand Does Not Necessarily Have the Highest Conversion

`runail` had the highest purchase volume with **45,274 purchases**.

However, `bpw.style` achieved a much stronger **22.95% view-to-purchase conversion rate**.

This shows that purchase volume alone is not enough to evaluate brand performance.

### Recommendation

Use both purchase volume and traffic-to-purchase efficiency when evaluating brands. This will help identify brands that convert traffic particularly effectively.

---

## 5. Price Outliers Should Be Investigated Separately

Approximately **6.91% of purchase prices** were identified as outliers using the IQR method.

Values above approximately **11.515** may be related to premium products, different product segments, or potential data quality problems.

### Recommendation

Outliers should be investigated rather than automatically deleted. If they represent legitimate premium products, they can be analyzed as a separate product segment.

---

# Visualizations

Several visualizations were created to communicate the main findings.

## Funnel Bar Chart

Shows the number of users at each stage:

**View → Cart → Purchase**

This helps identify where the largest drop-offs occur in the customer journey.

## Conversion Rate by Category

Compares conversion rates across product categories and highlights the strongest and weakest performers.

## January vs February Conversion Comparison

Compares monthly conversion rates and visually demonstrates the decline from January to February.

## Top 10 Brands

A horizontal bar chart displays the top 10 brands by purchase volume.

This provides a quick overview of the brands generating the largest number of purchases.

---

# Methodology

The analysis followed these main steps:

1. Load and inspect the dataset.
2. Check data types and missing values.
3. Prepare datetime columns.
4. Identify and separate `view`, `cart`, and `purchase` events.
5. Build the conversion funnel.
6. Calculate view-to-cart conversion rates.
7. Calculate view-to-purchase conversion rates.
8. Compare conversion performance between January and February.
9. Analyze conversion rates by product category.
10. Analyze brand performance using purchase volume and conversion efficiency.
11. Identify high-view, low-conversion products.
12. Calculate the time between view and purchase for converted users.
13. Detect price outliers using the IQR method.
14. Create visualizations to communicate the findings.
15. Develop business insights and recommendations.

---

# Business Recommendations

Based on the analysis, the following actions are recommended:

* Investigate the February conversion decline and identify the main sources of the decrease.
* Study the successful characteristics of the `apparel.glove` category.
* Review the customer journey and product pages of `accessories.bag`.
* Evaluate brands using both purchase volume and conversion efficiency.
* Optimize products with high traffic but low conversion.
* Review product pricing and investigate unusual price values.
* Analyze stock availability and delivery conditions for weak-performing products.
* Improve product images and descriptions where necessary.
* Test different promotional and pricing strategies.
* Monitor conversion performance regularly by month, category, product, and brand.

---

# Conclusion

The analysis demonstrates that e-commerce performance cannot be evaluated using purchase volume alone.

The conversion funnel provides a more detailed understanding of user behavior and highlights where potential business problems occur.

The January-to-February comparison shows a slight decline in overall conversion, while category-level analysis reveals significant differences between high- and low-performing categories.

The `apparel.glove` category demonstrates strong conversion efficiency, whereas `accessories.bag` shows substantial funnel drop-off. Brand-level analysis also shows that high purchase volume does not necessarily mean high conversion efficiency.

Finally, the price outlier analysis indicates that a notable share of purchase prices requires additional investigation to distinguish legitimate premium products from possible data quality issues.

Overall, the findings can be used to support **conversion optimization, product strategy, pricing decisions, brand evaluation, and customer experience improvements**.
