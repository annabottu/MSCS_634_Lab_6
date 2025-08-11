The dataset I chose was the instacart dataset, which has 6 different csv files -
  orders.csv which has the columns
    - order_id
    - user_id
    - eval_set
    - order_number
    - order_dow
    - order_hour_of_day
    - days_since_prior_order
  order_products_prioir.csv and order_products_train.csv
    - order_id
    - product_id
    - add_to_cart_order
    - reordered
  products.csv
    - product_id
    - product_name
    - aisle_id
    - department_id
  aisles.csv
    - aisle_id
    - aisle
  departments.csv
    - department_id
    - department

In this lab, I performed frequent itemset mining and association rule learning. After clearning and merging the data, I visualized product frequency and co-occurance patterns. I applied both Apriori and FP-Growth algorithms to find frequent itemsets, then generated association rules with support, confidence, and lift metrics, visualizing the strongest realtionship. After comparing the results between Apriori and FP-Growth, the cells above show that the runtime for Apriori was 24.49 seconds and the runtime for FP-Growth was 18.24 seconds, making FP-Growth faster. FP-Growth algorithm was faster for my dataset was because the instacart dataset has many items and becuase of that the Apriori algorithmn slows down as the number of products increase and FP-Growth is better for datasets with many products. Apriori requires the dataset to be pased through mutliple times, where that is not necessay for FP-Growth. Some of the challenges I faced was with memory overload issues, where the kernal would crash because of how much memory it was using, but I was able to resolve it mimiting the transaction to only 200K orders. I also had a problem with the heatmap, due to the huge number of item pairs. But I was able to resolve it by using pd.crosstab() and .T.dot() by filtering only the most popular products.
