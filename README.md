🛒 Market Basket Analysis using Apriori & FP‑Growth
Discovering purchasing patterns and cross‑selling opportunities from grocery transactions

📌 Overview
This project applies Market Basket Analysis techniques to uncover meaningful relationships between products in a grocery dataset. Using Apriori and FP‑Growth, the analysis identifies frequent itemsets, generates association rules, and visualises key insights that can support retail decision‑making.

The project includes:

Data preprocessing and one‑hot encoding

Frequent itemset mining

Association rule generation

Visualisations (bar charts, scatter plots, histograms, network graphs, heatmaps)

Strategic recommendations for retail optimisation

🧰 Tools & Technologies
Python

pandas

mlxtend (Apriori, FP‑Growth, association rules)

matplotlib / seaborn

networkx

Jupyter Notebook

📂 Dataset
The dataset contains thousands of real grocery transactions, each representing a customer’s basket.
It includes:

38,765 transactions

167 unique products

Items ranging from dairy and produce to beverages and household goods

⚙️ Methods
1. Preprocessing
Transactions are transformed into a one‑hot encoded matrix (basket_sets) suitable for frequent pattern mining.

2. Frequent Itemset Mining
Two algorithms are applied:

Apriori

FP‑Growth (preferred for efficiency)

Parameters used:

min_support = 0.07

use_colnames = True

3. Association Rule Generation
Rules are generated using:

min_confidence = 0.50

Metrics evaluated: support, confidence, lift

📊 Key Visualisations & Insights
Top 20 Most Frequent Items
Shows staple products such as whole milk, other vegetables, and rolls/buns, which dominate customer baskets and act as anchor items.

Support vs Confidence Scatter Plot
Most rules fall between 0.07–0.19 support and 0.51–0.60 confidence, confirming reliable but moderately frequent associations.

Lift Distribution
Lift values mostly range from 1.10 to 1.18, indicating positive but modest associations typical in grocery data.

Association Rule Network Graph
Highlights whole milk as a central hub connected to items like yogurt, pastry, domestic eggs, and bottled water — ideal for cross‑selling.

Item Co‑Occurrence Heatmap
Reveals broader item relationships beyond the strongest rules, offering deeper insight into basket composition.

🧠 Strategic Recommendations
1. Cross‑Selling Around Anchor Products
Use items like whole milk and vegetables as focal points for bundle deals and nearby complementary placement.

2. Store Layout Optimisation
Group frequently co‑purchased items to reduce search time and encourage larger baskets.

3. Targeted Promotions
Design discounts around high‑lift item pairs to maximise promotional impact.

4. Inventory Planning
Ensure consistent stock for high‑frequency items and anticipate demand spikes based on common combinations.

5. Online Recommendation Systems
Use association rules to power “Frequently Bought Together” suggestions in digital shopping platforms.
