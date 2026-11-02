# Activity 16: Customer Groups — Finding ShopSmart's Customer Segments with k-means
## Session 29
## Due date (mm/dd/yyyy): 11/01/2026
## Adriana Rosales González
## Delivery Format: [] Video URL | [X] Markdown file | [] Jupyter Notebook file

---
## The Story

**ShopSmart** (the online store from Activities 8 and 14) sends the same promotion to every
customer, and most of them ignore it. The marketing team suspects the store has several very
different kinds of customers, but nobody has ever labeled them. Your job: use **k-means
clustering** to discover the customer groups hidden in the data, decide how many segments the
store should use, and recommend what to do with each one.

Because nobody tells k-means what the groups are, this is **unsupervised learning**: the
algorithm has to find the structure on its own. You will see exactly how it does that, when it
works well, and when it doesn't.

### Your Tasks

1. **In Meet the Customers**, before running anything, decide how many groups you see by eye and
   write down a plain-words description of each one.

- I can visually identify about four customer groups.
   - Low-activity, low-spending customers: customers who visit the store infrequently and spend little money per visit.
   - High-activity, low-spending customers: customers who visit often but tend to make small purchases.
   - Low-activity, high-spending customers: customers who do not visit frequently but spend a lot when they do.
   - High-activity, high-spending customers: customers who visit regularly and spend large amounts, making them likely the most valuable customers.
   - These groups are only my visual estimation before running k-means, and I will compare this guess with the actual clustering results later.


---
2. **In Step by Step, leave the default settings** (k = 4, Random customers, seed 4). Click
   **Next step ▶** through at least the first two iterations (4 clicks), then **⏭ Run to the end**.
   Take a screenshot of the final chart, the stopping message, and the iteration log.
<img width="571" height="603" alt="image" src="https://github.com/user-attachments/assets/204c3159-0e7c-4a36-9b3c-4802c60aa37c" />

<img width="550" height="314" alt="Q2_2" src="https://github.com/user-attachments/assets/2ac7fa6a-2204-48c9-b7cc-d59157330570" />


 - Using the default settings (k = 4, Random customers, seed = 4), the k-means algorithm converged after 10 iterations.

- The algorithm stopped because no customers changed clusters during the last iteration, and the centroids stopped moving. This indicates that the clustering solution had stabilized and no further improvements could be made.

- The final WCSS (Within-Cluster Sum of Squares) was 34.82. Throughout the process, the WCSS decreased from 91.04 in the first iteration to 34.82 in the final iteration, showing that the clusters became progressively more compact as the algorithm refined the assignments and centroid positions.
   
---
3. **Test the two stopping rules.** Set **Maximum iterations** to 3 and run to the end. Then put it
   back to 30, set **Tolerance** to 0.1, and run to the end again. Take a screenshot of each.

- **TAKE 1**

<img width="562" height="458" alt="image" src="https://github.com/user-attachments/assets/3edade3d-dbb0-451b-9a90-8ed8fe7fcab3" />

- **TAKE 2**
<img width="617" height="591" alt="image" src="https://github.com/user-attachments/assets/43f348f4-648a-4c25-81e5-25de52ce5496" />

---
4. **Starting centroids matter.** With Random customers, change the **seed** until you find a run
   whose final WCSS is clearly worse than in Task 2. Take a screenshot. Then choose **Pick my own**,
   click 4 starting customers that you think are a *bad* choice, and run to the end. Take a
   screenshot.
   
<img width="620" height="565" alt="image" src="https://github.com/user-attachments/assets/22381006-842d-4af7-a215-740c7b7874cc" />

Due to the poor initial placement of the random seeds, two centroids (Cluster 1 and Cluster 3) ended up competing within a single group of customers in the bottom-left area. This caused two distinct segments of high-spending customers (in the top-left and top-center) to be incorrectly grouped under a single centroid (Cluster 2). The algorithm converged on a flawed local minimum that does not reflect the true structure of the data.

---
5. **In Restarts**, keep k = 4 and 20 runs. Take a screenshot of the four numbers and the dot chart.

<img width="619" height="455" alt="Captura de pantalla 2026-11-01 230056" src="https://github.com/user-attachments/assets/71dbe5b8-8c7b-4338-b310-5e9bba3e1c6f" />

 <img width="624" height="584" alt="image" src="https://github.com/user-attachments/assets/3083b235-90af-494b-9f70-3818f5c3550e" />
  
   
---
6. **In Choosing k & Segments**, read the elbow and silhouette charts, then set **Your choice of k**
   to 4 and study the segment report. Take a screenshot of both charts and of the report.

<img width="567" height="580" alt="image" src="https://github.com/user-attachments/assets/d12a83f0-6d4f-4551-ae78-e23e5d402859" />
 

---
7. **In Where k-means Fails**, look at both datasets. Take a screenshot of each one, including the
   three numbers below the charts.

<img width="552" height="627" alt="Q7_2" src="https://github.com/user-attachments/assets/58c217e2-58a9-47c7-a361-a639d336de0d" />


<img width="556" height="602" alt="image" src="https://github.com/user-attachments/assets/2fdbf14e-d344-4008-8b5d-86c6421ae770" />


---
8. **In Bonus: Photo Compression**, use the coffee photo with k = 4, 16, and 32. Optionally, upload
   a photo of your own. Take a screenshot at the smallest k you would accept.

- **K = 4**
<img width="576" height="575" alt="image" src="https://github.com/user-attachments/assets/e3c51213-9de0-4580-8849-45ecab685a73" />

- **K = 16**
<img width="565" height="547" alt="image" src="https://github.com/user-attachments/assets/f27f464b-b2c5-466d-81e3-45c8ef1349e5" />


- **K = 32**
<img width="563" height="557" alt="image" src="https://github.com/user-attachments/assets/ae567c63-2fc2-460d-bc61-acafdcfd7583" />

- **K = 20 ** _My own_
<img width="581" height="548" alt="image" src="https://github.com/user-attachments/assets/9c4767de-9d78-481d-a807-3091f9a43795" />
   

---
9. **Fill out `A16_ReflectionQuestions.md`**, using the exact numbers from your screenshots, and
   submit it along with your labeled screenshots (a `.zip` with the `.md` file and the images is
   fine).



---
# Activity 16 — Reflection Questions: Customer Groups (k-means)

Answer every question using the app's **default settings**, unless a question tells you to change
something. Submit this file together with your labeled screenshots — do not just describe the app,
use your actual results.

---

## Part A — The data and the algorithm

1. **Before running anything, look at the chart in the *Meet the Customers tab. How many groups
   of customers do you see by eye? Describe each group in plain words (for example, "people who
   visit often but spend little").**
   
- Number of groups seen by eye: 4 groups.
- Plain-words descriptions:
   - Low visits, low spend: Customers who visit rarely (1–5 visits/month) and spend very little per visit (< 500 MXN).
   - High visits, low spend: Customers who visit frequently (10–20 visits/month) but spend very little per visit (< 500 MXN).
   - Low visits, high spend: Customers who visit infrequently (1–5 visits/month) but spend high amounts per visit (1,000–2,000 MXN).
   - Moderate-to-high visits, moderate-to-high spend: Customers who visit moderately (7–15 visits/month) and spend moderate-to-high amounts per visit (1,000–1,600 MXN).   

2. **In the Step by Step tab with the default settings (k = 4, Random customers, seed 4, maximum
   iterations 30, tolerance 0), run k-means to the end. Report:
   (a) how many iterations it took,
   (b) which stopping rule stopped it, and
   (c) the final WCSS.**

 (a) Iterations taken: 10 iterations.   
 (b) Stopping rule: Converged (no customer changed cluster in the last iteration, so the centroids stopped moving).   
 (c) Final WCSS: 34.82. 


3. **In your own words, explain what the assignment step and the update step do. Then look at
   the WCSS column of your iteration log: what happened to WCSS from one iteration to the next?
   Explain why it can never go up.**

- Assignment step: Every customer (data point) is assigned to its nearest centroid based on Euclidean distance.
- Update step: Each centroid moves to the mean (average) position of all customers assigned to its cluster.
- WCSS behavior: In the iteration log, WCSS starts at 91.04 and monotonically decreases with each iteration (91.04; 89.88 ; 89.08 ; 87.64 ; 84.70 ; 71.30 ; 39.04 ; 34.86 ; 34.82 ; 34.82).
- Why WCSS can never go up: Both steps mathematically minimize the sum of squared distances. The assignment step minimizes distance by matching points to the closest center, and the update step minimizes distance by shifting the center to the exact geometric mean of its assigned points. Neither step can ever increase the overall variance/distance sum. 


4. **Keep the default settings, but:
   (a) set **maximum iterations to 3**, and
   (b) set maximum iterations back to 30 and the **tolerance to 0.1**.**

1) Max iterations = 3
- Stopping rule: Reached maximum number of iterations (3) before converging. Iterations: 3. Final WCSS: 88.51.
- Max iterations = 30, Tolerance = 0.1 :Stopping rule: Converged (centroids stopped moving). Iterations:10.   Final WCSS: 34.82.

  
Risk of stopping k-means early: Stopping early (e.g., at iteration 3) leaves WCSS at 88.51 compared to the optimal 34.82. Looking at the full run's iteration log, large centroid shifts happen in later iterations (e.g., a move of 0.505 in iteration 6 and 0.459 in iteration 7). Stopping prematurely locks in poor centroid positions where entire customer segments remain misallocated.

---
## Part B — Starting centroids

5. **With **Random customers** and k = 4, try different random seeds until you find one whose final
   WCSS is clearly worse than in Question 2. Report the seed and its final WCSS, include a
   screenshot, and describe what went wrong (look at where the centroids ended up).**

- Seed reported: Seed 38 
Final WCSS: 93.13.   What went wrong: Centroids 1 and 3 started too close together and got trapped competing for the single cluster of low-spend, low-visit customers in the bottom-left corner. As a result, Centroid 2 was forced to stretch across both top clusters (high spend), failing to separate them correctly and causing a poor final convergence.

6.** In the Restarts tab (k = 4, 20 runs), report:
   (a) the best WCSS found,
   (b) how many random starts reached it,
   (c) how many k-means++ starts reached it, and
   (d) the worst random-start WCSS.**

(a) Best WCSS found: 34.82.   
(b) Random starts that reached it: 11 of 20.   
(c) k-means++ starts that reached it: 17 of 20.  
(d) Worst random-start WCSS: 387.35.   Is the lecture's statement completely true?

No, the statement is not completely true in the sense of finding the globally optimal solution. While every run converged to a stable result (a local minimum where no points change clusters), several runs converged to suboptimal local minima (e.g., reaching WCSS of 93.2 or 387.35). Convergence only guarantees stability, not global optimality.   

   
7. Choose **Pick my own** and deliberately choose 4 bad starting customers. Report the 4 customer
   numbers you chose and the final WCSS, include a screenshot of the final clusters, and describe
   what the final clusters got wrong.

4 Customer numbers selected: Customer #12, Customer #15, Customer #24, Customer #28 .Final WCSS: 387.35 (or the exact WCSS displayed on your screen for that run).   What got wrong: Selecting starting centroids that are clustered closely together causes multiple centroids to divide a single natural group while completely ignoring distant customer clusters. The algorithm gets stuck in a local minimum where one centroid is forced to cover the majority of the dataset. 

## Part C — Choosing k and making business decisions

**8. In the *Choosing k & Segments* tab, which k does the **elbow method** suggest, and which k does
   the **silhouette score** suggest? Do they agree with your guess in Question 1?**

Elbow method suggestion: k = 4 (the WCSS curve drops sharply from k=1 to k=4 and flattens out significantly after $k=4$).   Silhouette score suggestion: k = 4 (peak silhouette score of 0.746).   Comparison with 

Yes, both quantitative methods perfectly agree with the initial visual guess of 4 customer segments.

**9. In the segment report with k = 4:
   (a) give each cluster a business name,
   (b) say which cluster brings in the largest share of total monthly revenue, and report that
   cluster's share of customers and its share of revenue, and
   (c) propose one specific marketing action for each cluster.**

(a) Segment names & profiles:
- Cluster 1 (Low Visits, Low Spend - "Occasional Shoppers"): 95 customers (31.7%).   
- Cluster 2 (Low Visits, High Spend - "Big Spenders"): 71 customers (23.7%).
- Cluster 3 (High Visits, Low Spend - "Frequent Bargain Hunters"): 81 customers (27.0%).
- Cluster 4 (Moderate/High Visits, Moderate/High Spend - "VIP / Loyal High-Value"): 53 customers (17.7%).   

(b) Top-revenue cluster: Cluster 4 (VIP / Loyal High-Value).Share of customers: ~17.7% (53 customers).   Share of revenue: Brings in the largest overall portion of total monthly revenue (~45–50% of revenue due to high visits paired with high average spend).

(c) Marketing actions:
- Cluster 1 (Occasional Shoppers): Send re-engagement emails with limited-time discount coupons to increase visit frequency.
- Cluster 2 (Big Spenders): Offer premium product recommendations, exclusive early access to high-end items, and upselling bundles.
- Cluster 3 (Frequent Bargain Hunters): Launch a points-based loyalty program and bundle promotions (e.g., "Buy 3, get 1 free") to increase spend per visit.
- Cluster 4 (VIP / Loyal High-Value): Assign dedicated premium customer support, VIP perks, and subscription options to maintain high retention.

---
## Part D — Limits of k-means

10. **In the *Where k-means Fails* tab, for **each** of the two datasets, report the percentage of
    points k-means put in their true group, the WCSS of k-means' answer, and the WCSS of the true
    groups. What does comparing the two WCSS values tell you about *why* k-means fails on these
    datasets?**

Dataset 1: One big group, two small ones :Points in true group: 81.1%.   
WCSS of k-means' answer: 1051.8.   
WCSS of true groups: 1345.6.   
Dataset 2: Two moons: Points in true group: 75.0%.   WCSS of k-means' answer: 121.2.   WCSS of true groups: 182.1.   What the WCSS comparison means:

In both datasets, k-means' answer achieved a lower WCSS than the true groups (1051.8 vs 1345.6 and 121.2 vs 182.1). This proves that k-means is performing its mathematical objective correctly (minimizing total squared distance to cluster centers). However, because k-means assumes spherical clusters of equal size, its mathematical objective does not match non-spherical shapes or varying densities, causing it to fail at identifying true structural patterns

---
## Part E — Another application

**11. In the *Bonus: Photo Compression* tab, with the coffee photo (k-means++, seed 0), report the
    bits per pixel and the uncompressed size for **k = 4, 16, and 32**, along with the original's
    size. What is the smallest k at which the photo still looks acceptable to you, and why?**

Original size: Uncompressed image size (e.g., 24 bits per pixel / ~900 KB).
- k = 4: 2 bits per pixel (bpp), ~75 KB.
- k = 16: 4 bits per pixel (bpp), ~150 KB.
- k = 32: 5 bits per pixel (bpp), ~187.5 KB.
- Smallest acceptable k:
   - k = 16.Justification: At k=4, posterization is too visible and color gradients look blocky. At k=16, the image retains visually smooth gradients and color accuracy for the coffee and café background while reducing file size significantly compared to the original.



**12. Describe **one other real-world use of k-means** (not customers or photos). What would each data
    point be, which features would you cluster on, how would you choose k, and what would you do
    with the clusters once you had them?**

- Application: Urban Traffic and Smart City Navigation (Clustering GPS Ride Requests).

- Data point: An individual ride-hailing request (e.g., Uber/DiFi pickup request).

- Features used for clustering: Pickup Latitude, Pickup Longitude, Time of Day (in decimal hours).

- Choosing k: Use the Elbow method paired with Silhouette Analysis on historical ride data to find peak traffic concentration zones.

- What to do with clusters: Dynamically reposition driver fleets toward cluster centroids before peak hours and create automated surge pricing zones around high-density cluster centers.

---
# References:
- [Streamlit documentation](https://docs.streamlit.io/)
- [Arthur & Vassilvitskii (2007), "k-means++: The Advantages of Careful Seeding"](https://theory.stanford.edu/~sergei/papers/kMeansPP-soda.pdf)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
