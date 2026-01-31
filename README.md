<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Market Basket Analysis – Apriori & FP-Growth</title>
  <style>
    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      margin: 0;
      padding: 0;
      background: #0f172a;
      color: #e5e7eb;
      line-height: 1.6;
    }
    .hero {
      padding: 60px 20px;
      text-align: center;
      background: radial-gradient(circle at top, #1d4ed8 0, #020617 55%);
      color: #f9fafb;
    }
    .hero h1 {
      font-size: 2.6rem;
      margin-bottom: 10px;
    }
    .hero h2 {
      font-size: 1.2rem;
      font-weight: 400;
      color: #cbd5f5;
      margin-top: 0;
    }
    .hero p {
      max-width: 700px;
      margin: 15px auto 0;
      color: #e5e7eb;
    }
    .tagline {
      display: inline-block;
      margin-top: 18px;
      padding: 6px 14px;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.7);
      border: 1px solid rgba(148, 163, 184, 0.5);
      font-size: 0.85rem;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      color: #cbd5f5;
    }
    .container {
      max-width: 960px;
      margin: 0 auto;
      padding: 30px 20px 60px;
    }
    h3 {
      margin-top: 30px;
      font-size: 1.3rem;
      color: #e5e7eb;
      border-bottom: 1px solid #1f2937;
      padding-bottom: 6px;
    }
    p {
      color: #d1d5db;
      margin-top: 10px;
    }
    ul {
      margin-top: 8px;
      padding-left: 20px;
      color: #d1d5db;
    }
    li {
      margin-bottom: 4px;
    }
    .pill-row {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 10px;
    }
    .pill {
      padding: 4px 10px;
      border-radius: 999px;
      background: #111827;
      border: 1px solid #374151;
      font-size: 0.8rem;
      color: #e5e7eb;
    }
    .footer {
      text-align: center;
      font-size: 0.8rem;
      color: #6b7280;
      padding: 20px 0 30px;
      border-top: 1px solid #111827;
      margin-top: 30px;
    }
    a {
      color: #60a5fa;
      text-decoration: none;
    }
    a:hover {
      text-decoration: underline;
    }
    code {
      background: #020617;
      padding: 2px 5px;
      border-radius: 4px;
      font-size: 0.85rem;
      color: #e5e7eb;
    }
  </style>
</head>
<body>

  <section class="hero">
    <span class="tagline">Market Basket Analysis · Groceries Dataset</span>
    <h1>Market Basket Analysis with Apriori & FP-Growth</h1>
    <h2>Discovering purchasing patterns and cross‑selling opportunities from 38,765 grocery transactions</h2>
    <p>
      This project applies classical association rule mining techniques to a real‑world groceries dataset,
      using Apriori and FP‑Growth to uncover frequent itemsets, strong association rules, and actionable
      retail strategies.
    </p>
  </section>

  <main class="container">
    <section>
      <h3>Project Overview</h3>
      <p>
        The goal of this analysis is to understand how customers combine products in their baskets and to
        translate those patterns into practical decisions for product placement, promotions, and inventory
        planning. Using a one‑hot encoded transaction matrix, frequent itemsets are mined and association
        rules are generated and evaluated.
      </p>
      <div class="pill-row">
        <span class="pill">Python · pandas · mlxtend</span>
        <span class="pill">Apriori</span>
        <span class="pill">FP‑Growth</span>
        <span class="pill">Association Rules</span>
        <span class="pill">Support · Confidence · Lift</span>
      </div>
    </section>

    <section>
      <h3>Methods & Parameters</h3>
      <p>
        Transactions are transformed into a one‑hot encoded basket representation and analysed using both
        Apriori and FP‑Growth. FP‑Growth is ultimately preferred for its efficiency while producing identical
        frequent itemsets.
      </p>
      <ul>
        <li><strong>Dataset size:</strong> 38,765 transactions, 167 unique products</li>
        <li><strong>Frequent itemsets:</strong> mined with <code>min_support = 0.07</code></li>
        <li><strong>Association rules:</strong> generated with <code>min_confidence = 0.50</code></li>
        <li><strong>Key metrics:</strong> support, confidence, lift</li>
      </ul>
      <p>
        These thresholds strike a balance between capturing meaningful patterns and keeping the number of
        rules interpretable and actionable.
      </p>
    </section>

    <section>
      <h3>Key Insights from Visualisations</h3>
      <ul>
        <li>
          <strong>Top 20 Most Frequent Items:</strong>
          <em>Whole milk</em>, <em>other vegetables</em>, and <em>rolls/buns</em> dominate baskets,
          acting as staple anchor products.
        </li>
        <li>
          <strong>Support vs Confidence:</strong>
          Rules cluster between 0.07–0.19 support and 0.51–0.60 confidence, confirming that the chosen
          thresholds yield moderately frequent yet reliable rules.
        </li>
        <li>
          <strong>Lift Distribution:</strong>
          Most rules have lift values slightly above 1, indicating positive but modest associations—typical
          for diverse grocery data.
        </li>
        <li>
          <strong>Network Graph:</strong>
          <em>Whole milk</em> emerges as a central hub, strongly connected to items such as yogurt, pastry,
          domestic eggs, bottled water, and shopping bags.
        </li>
        <li>
          <strong>Co‑Occurrence Heatmap:</strong>
          Highlights broader item pairings and category‑level relationships that extend beyond the strongest
          rules, enriching understanding of basket composition.
        </li>
      </ul>
    </section>

    <section>
      <h3>Strategic Recommendations</h3>
      <ul>
        <li>
          <strong>Cross‑selling around anchor products:</strong>
          Use whole milk, other vegetables, and rolls/buns as focal points for nearby complementary items
          and bundle promotions.
        </li>
        <li>
          <strong>Layout optimisation:</strong>
          Group frequently co‑purchased items to reduce search time and encourage larger baskets
          (e.g. fresh essentials zones combining vegetables, fruit, and dairy).
        </li>
        <li>
          <strong>Promotion design:</strong>
          Target discounts and loyalty offers on items with strong lift and frequent co‑occurrence with
          staples to maximise response.
        </li>
        <li>
          <strong>Inventory planning:</strong>
          Prioritise stock availability for high‑frequency items and anticipate demand spikes based on
          common combinations (e.g. milk + eggs + pastry around weekends).
        </li>
        <li>
          <strong>Online recommendations:</strong>
          Use association rules to power “frequently bought together” suggestions and personalised
          recommendations in digital channels.
        </li>
      </ul>
    </section>

    <section>
      <h3>Repository Contents</h3>
      <ul>
        <li><strong>Notebook:</strong> full Market Basket Analysis workflow (preprocessing, FP‑Growth, Apriori, rules, visualisations)</li>
        <li><strong>Figures:</strong> bar charts, scatter plots, histograms, network graph, and heatmap</li>
        <li><strong>Report sections:</strong> conclusions and strategic recommendations for retail decision‑making</li>
      </ul>
    </section>

    <div class="footer">
      <p>Market Basket Analysis · Apriori & FP‑Growth · Groceries Dataset</p>
    </div>
  </main>

</body>
</html>
