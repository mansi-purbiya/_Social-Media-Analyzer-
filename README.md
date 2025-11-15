<h1>📊 Social Media Analyzer (Power BI)</h1>

<p>
This project is a <strong>Power BI Dashboard</strong> designed to analyze Instagram-style social media performance. 
It measures engagement, reach, impressions, and post performance using an interactive dashboard.  
</p>

<hr>

<h2>🎯 Project Overview</h2>

<p>
This Power BI dashboard helps identify:
</p>

<ul>
  <li>✔ Total posts & engagement</li>
  <li>✔ Engagement trends over time</li>
  <li>✔ Best-performing posts</li>
  <li>✔ Content type performance (Reel, Video, Image)</li>
  <li>✔ Reach vs Engagement relationships</li>
  <li>✔ Best day/time to post</li>
</ul>

<hr>

<h2>📥 Dataset Used</h2>

<p><strong>instagram_sample_dataset.csv</strong> contains:</p>

<ul>
  <li>Post_ID</li>
  <li>Post_Date</li>
  <li>Content_Type (Reel / Image / Video)</li>
  <li>Likes, Comments, Shares, Saves</li>
  <li>Reach & Impressions</li>
  <li>Video Views</li>
  <li>Hashtags</li>
</ul>

<hr>

<h2>⚙️ Data Modeling (DAX Formulas)</h2>

<h3>📌 Calculated Columns</h3>

<pre><code>
Post_Engagement =
instagram_sample_dataset[Likes] +
instagram_sample_dataset[Comments] +
instagram_sample_dataset[Shares] +
instagram_sample_dataset[Saves]

Post_Engagement_Rate =
DIVIDE(instagram_sample_dataset[Post_Engagement],
       instagram_sample_dataset[Reach], 0)

Post_Day = FORMAT(instagram_sample_dataset[Post_Date], "dddd")
Post_Month = FORMAT(instagram_sample_dataset[Post_Date], "MMMM")
</code></pre>

<h3>📌 Measures</h3>

<pre><code>
Total Posts = COUNTROWS(instagram_sample_dataset)

Total Engagement = SUM(instagram_sample_dataset[Post_Engagement])

Avg Engagement Per Post =
DIVIDE([Total Engagement], [Total Posts])

Engagement Rate =
DIVIDE([Total Engagement], SUM(instagram_sample_dataset[Reach]))
</code></pre>

<hr>

<h2>📊 Dashboard Pages</h2>

<h3>1️⃣ Page 1 — Overview</h3>
<ul>
  <li>KPI Cards</li>
  <li>Engagement line chart</li>
  <li>Content type pie chart</li>
  <li>Engagement by content type bar chart</li>
</ul>

<h3>2️⃣ Page 2 — Content Performance</h3>
<ul>
  <li>Post performance table</li>
  <li>Top 10 posts bar chart</li>
  <li>Scatter chart (Reach vs Engagement vs Impressions)</li>
</ul>

<h3>3️⃣ Page 3 — Posting Strategy</h3>
<ul>
  <li>Heatmap (Day × Month or Day × Hour)</li>
  <li>Hashtag analysis</li>
  <li>Recommendations section</li>
</ul>

<hr>

<h2>📈 How to Interpret Charts</h2>

<h3>✔ Line Chart</h3>
<p>Shows engagement trend across dates. Peaks = high-performing days, dips = low engagement days.</p>

<h3>✔ Top Posts Bar Chart</h3>
<p>Highlights posts with the highest engagement.</p>

<h3>✔ Scatter Chart</h3>
<ul>
  <li>Right side = higher reach</li>
  <li>Upper side = higher engagement</li>
  <li>Bigger bubble = more impressions</li>
</ul>

<hr>
