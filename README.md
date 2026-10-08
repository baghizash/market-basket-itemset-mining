# Market Basket Itemset Mining

Mining frequent purchase patterns from grocery order data: which products sell the most, which products are bought together, and how similar two baskets are.

Coursework from **Data Mining in Python** (University of Michigan, More Applied Data Science with Python specialization). All notebooks run end to end with outputs.

## Data

`data/` holds the course-provided sample of **10,000 Instacart grocery orders**:

- `orders.csv.zip` — order lines: `order_id`, `product_id`
- `products.csv.zip` — product catalog mapping `product_id` to `product_name`

## What was done

**Part 1 — Top products** (`notebooks/part1-top-products.ipynb`)
Exploratory analysis of the transaction data: order-size distribution and the most frequently purchased products. Implemented `top_n_products(n)`, which returns the n most popular product names. Result: **Banana** and **Bag of Organic Bananas** are the two most popular products.

**Part 2 — Frequent itemsets with Apriori** (`notebooks/part2-apriori-frequent-itemsets.ipynb`)
Implemented `prod_frequent_itemsets` on top of the Apriori algorithm (mlxtend) to find product combinations that are frequently bought together, with exact itemset-length filtering. Also implemented `mi()`, the mutual information between two binary variables (base-2 log, zero-probability terms skipped), first practiced on a sample of 10,000 tweets containing food/drink emojis. This is the "frequently bought together" engine behind e-commerce recommendations.

**Part 3 — Jaccard similarity** (`notebooks/part3-jaccard-similarity.ipynb`)
Implemented `jaccard_similarity(set_a, set_b) = |A ∩ B| / |A ∪ B|` and established its range: minimum **0**, maximum **1**. Applied it to find the tweets most similar to a given tweet in terms of emoji usage.

## Tech

Python, pandas, NumPy, matplotlib, mlxtend (Apriori), Jupyter.
