Online vs In‑Store Retail Transaction Analysis

Executive Summary

This data science project explores purchasing behaviour using a publicly available retail dataset to assess whether online purchases are typically higher or lower in value than in‑store purchases and the implications for encouraging digital sales.

The analysis uses the Retail Store Sales – Dirty Data dataset from Kaggle, which contains transaction‑level sales data and is intentionally imperfect, making it well suited to demonstrating practical data science skills such as data cleaning, preparation, exploratory analysis, and visualisation.

Using structured data cleaning techniques and descriptive analysis, transaction values were compared across online and in‑store channels, examining differences in average and median basket value, distributional mix, category‑level behaviour, and the impact of discounting.

The findings show that online purchases are not inherently higher or lower in value than in‑store purchases. Instead, transaction value differences are driven primarily by basket composition, product category, and promotion design rather than channel alone. These insights support evidence‑based recommendations focused on improving online basket value through targeted promotions and basket‑building strategies, rather than blanket discounting, and highlight opportunities for future enhancement such as customer segmentation and predictive modelling.

 

Data Source and Initial Exploration

The dataset used is the Retail Store Sales – Dirty Data dataset sourced from Kaggle (Mohamed, 2025). It contains approximately 12,500 transaction‑level records, including variables such as product category, quantity, price per unit, purchase channel (online or in‑store), transaction date, and discount flag.

The dataset is intentionally “dirty”, containing inconsistent formatting, missing values, and duplicated records. An initial exploratory review identified data quality issues that required cleansing to ensure reliable comparison of transaction values across purchase channels.

 

Data Cleaning and Preparation

Data preparation was undertaken using Excel Power Query to create a transparent, repeatable ETL workflow with an auditable step log. Power Query was appropriate for the dataset size (~12,500 records), enabling consistent type enforcement, deduplication, and feature engineering with refresh capability. A limitation is that Excel is less suited to advanced modelling or large‑scale pipelines; future iterations could replicate the workflow in Python (pandas) and Power BI.

Key cleaning steps included standardising column names, explicitly assigning data types, and normalising the purchase location field to ensure only two valid values (“Online” and “In‑Store”). Transactions with missing or invalid price or quantity values were removed to ensure reliable transaction value calculation.

Total spend was recalculated, duplicates removed, and values standardised to GBP (£). Transaction value bands (Low, Mid, High) were created to support distributional analysis, producing an analysis‑ready dataset.

 

Hypothesis

H₀ (Null hypothesis): There is no meaningful difference in transaction value between online and in‑store purchases.
H₁ (Alternative hypothesis): Online purchases are typically higher in value than in‑store purchases.

The hypothesis was evaluated using descriptive analytics, comparing average and median transaction values and examining distributional effects across channels.

 

Analysis

Channel‑level Transaction Value

Initial analysis compared average and median transaction value across purchase channels. Mean transaction value is almost identical for online and in‑store transactions (£130 online vs £129 in‑store), and median transaction value is identical (£109 for both). This indicates that typical basket size does not differ meaningfully by channel.

Total transaction spend is slightly higher online (£749k) than in‑store (£724k), reflecting a marginally higher number of online transactions. Given similar basket values, this difference appears to be volume‑led rather than value‑led.

 ../../images/image001.png

Transaction Value Mix by Channel

To explore distributional differences beneath similar averages, transactions were analysed by value band (Low, Mid, High). While overall value mix is broadly similar, online shows a modest shift away from low‑value baskets towards mid‑value transactions.

From a commercial perspective, this supports strategies focused on nudging low‑value baskets into mid‑value baskets online, such as threshold incentives and bundling, rather than broad discounting.

 

Category‑level Channel Differences

Category‑level analysis shows that channel differences are category‑driven rather than uniform. Online transactions exhibit higher average spend in Food and Computers / Electrical Accessories (approximately +£5) and in Butchers and Electric Household Essentials (approximately +£4). In contrast, in‑store transactions retain a small advantage in Furniture and Milk Products.

A channel delta view highlights categories where online performs strongly and where it underperforms. These findings indicate that efforts to grow online basket value should be category‑specific, focusing on strengthening already strong categories and addressing friction where in‑store retains an advantage.

 

Discount Impact on Transaction Value

The impact of discounting was assessed by comparing average transaction value for discounted and non‑discounted purchases across both channels. Without discounting, online transactions have a higher average value than in‑store purchases (£131.35 vs £128.90). When discounts are applied, average values converge.

Within‑channel analysis shows that discounting is associated with a modest increase in in‑store spend, while online average spend slightly decreases under discounting. This suggests that discounting may be a more effective lever in‑store than online, where promotions may capture transactions that would have occurred regardless.

 

Ethical Considerations and Limitations

This project uses a publicly available synthetic dataset for educational purposes, which may not fully represent real‑world retail behaviour. Removing transactions with missing values may introduce bias if missingness is not random.

The analysis relies on descriptive techniques and identifies associations rather than causality. Findings should therefore be validated using real organisational data and, where appropriate, controlled testing such as A/B experiments.

No personal or sensitive data was used, and no data protection risks were identified. Applying similar analysis in a live business setting would require consideration of customer fairness and promotion targeting bias.

 

Interpretation and Recommendations

Online purchases are not inherently higher or lower in value than in‑store purchases; instead, transaction value differences are driven by basket composition, product category, and promotion design. To encourage higher‑value online baskets, retailers should prioritise category‑specific strategies, focusing on categories where online already performs strongly and addressing barriers where in‑store retains an advantage.

Basket‑building interventions such as threshold‑based incentives, bundling, and cross‑sell prompts should be prioritised over blanket discounting. These interventions are low‑complexity to trial digitally and could be evaluated through controlled testing before wider roll‑out.

 

Future Improvements

Future enhancements could incorporate customer‑level segmentation to understand variation in basket behaviour across customer types. Time‑based analysis could explore seasonality or promotional effects, while predictive modelling could be used to identify drivers of high‑value baskets and support more proactive promotion targeting.
