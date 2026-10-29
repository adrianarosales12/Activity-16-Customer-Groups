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

   > 💡 **Hint:** There is no wrong answer here. Hover over any dot to see that customer's numbers.
   > You will compare this guess with what k-means finds in Task 6.

2. **In Step by Step, leave the default settings** (k = 4, Random customers, seed 4). Click
   **Next step ▶** through at least the first two iterations (4 clicks), then **⏭ Run to the end**.
   Take a screenshot of the final chart, the stopping message, and the iteration log.

   > 💡 **Hint:** In each **assignment** step, watch which customers change color. In each
   > **update** step, watch where the ✕ centroids move: each one jumps to the middle (average) of
   > its own customers. The dotted lines are the centroids' trails.

3. **Test the two stopping rules.** Set **Maximum iterations** to 3 and run to the end. Then put it
   back to 30, set **Tolerance** to 0.1, and run to the end again. Take a screenshot of each.

   > 💡 **Hint:** Compare each final WCSS with the one from Task 2. In the full run's iteration log
   > from Task 2, look at the "largest centroid move" column: does a small move always mean the
   > clusters are finished?

4. **Starting centroids matter.** With Random customers, change the **seed** until you find a run
   whose final WCSS is clearly worse than in Task 2. Take a screenshot. Then choose **Pick my own**,
   click 4 starting customers that you think are a *bad* choice, and run to the end. Take a
   screenshot.

   > 💡 **Hint:** Try putting all your starting customers in the same corner of the chart. Clicking
   > a customer adds it as a starting centroid (a yellow star); **Clear my picks** starts over.

5. **In Restarts**, keep k = 4 and 20 runs. Take a screenshot of the four numbers and the dot chart.

   > 💡 **Hint:** Each dot is one *complete* run that converged. If every run converged, why don't
   > they all have the same WCSS?

6. **In Choosing k & Segments**, read the elbow and silhouette charts, then set **Your choice of k**
   to 4 and study the segment report. Take a screenshot of both charts and of the report.

   > 💡 **Hint:** The *elbow* is where the WCSS curve bends and then flattens. For the silhouette, look
   > for the highest point. In the report, compare each cluster's **share of customers** with its
   > **share of revenue**.

7. **In Where k-means Fails**, look at both datasets. Take a screenshot of each one, including the
   three numbers below the charts.

   > 💡 **Hint:** Compare "WCSS of k-means' answer" with "WCSS of the true groups". Which one is
   > lower, and what does that say about what k-means is trying to do?

8. **In Bonus: Photo Compression**, use the coffee photo with k = 4, 16, and 32. Optionally, upload
   a photo of your own. Take a screenshot at the smallest k you would accept.

   > 💡 **Hint:** The sizes below the images depend only on the image size and on k. Compare the
   > pictures, not just the numbers.

9. **Fill out `A16_ReflectionQuestions.md`**, using the exact numbers from your screenshots, and
   submit it along with your labeled screenshots (a `.zip` with the `.md` file and the images is
   fine).

   > 💡 **Hint:** Before submitting, check each answer against **How Your Grade Is Calculated**
   > below. It lists exactly what earns full points on every question.





### About the Data and Photos

The 300 ShopSmart customers and the two "Where k-means Fails" datasets are fictional, generated
with a fixed random seed so that everyone sees exactly the same data. The photos come from the
scikit-image project's sample data:
- *coffee*: Rachel Michetti, courtesy of Pikolo Espresso Bar (CC0).
- *chelsea*: Stéfan van der Walt (CC0).
- *astronaut*: NASA, astronaut Eileen Collins (public domain).

---
# Activity 16 — Reflection Questions: Customer Groups (k-means)

Answer every question using the app's **default settings**, unless a question tells you to change
something. Submit this file together with your labeled screenshots — do not just describe the app,
use your actual results.

---

## Part A — The data and the algorithm

1. **Before running anything**, look at the chart in the *Meet the Customers* tab. How many groups
   of customers do you see by eye? Describe each group in plain words (for example, "people who
   visit often but spend little").

2. In the *Step by Step* tab with the default settings (k = 4, Random customers, seed 4, maximum
   iterations 30, tolerance 0), run k-means to the end. Report:
   (a) how many iterations it took,
   (b) which stopping rule stopped it, and
   (c) the final WCSS.

3. In your own words, explain what the **assignment step** and the **update step** do. Then look at
   the WCSS column of your iteration log: what happened to WCSS from one iteration to the next?
   Explain why it can never go up.

4. Keep the default settings, but:
   (a) set **maximum iterations to 3**, and
   (b) set maximum iterations back to 30 and the **tolerance to 0.1**.

   For each run, report the stopping rule, the number of iterations, and the final WCSS. Compare
   them with your answer to Question 2. What is the risk of stopping k-means early? (Hint: look at
   the "largest centroid move" column of the full run's log.)

## Part B — Starting centroids

5. With **Random customers** and k = 4, try different random seeds until you find one whose final
   WCSS is clearly worse than in Question 2. Report the seed and its final WCSS, include a
   screenshot, and describe what went wrong (look at where the centroids ended up).

6. In the *Restarts* tab (k = 4, 20 runs), report:
   (a) the best WCSS found,
   (b) how many random starts reached it,
   (c) how many k-means++ starts reached it, and
   (d) the worst random-start WCSS.

   The lecture says that when k-means converges, it "has reached an optimal and stable result."
   Every one of these runs converged. Based on your numbers, is the lecture's statement completely
   true? Explain.

7. Choose **Pick my own** and deliberately choose 4 bad starting customers. Report the 4 customer
   numbers you chose and the final WCSS, include a screenshot of the final clusters, and describe
   what the final clusters got wrong.

## Part C — Choosing k and making business decisions

8. In the *Choosing k & Segments* tab, which k does the **elbow method** suggest, and which k does
   the **silhouette score** suggest? Do they agree with your guess in Question 1?

9. In the segment report with k = 4:
   (a) give each cluster a business name,
   (b) say which cluster brings in the largest share of total monthly revenue, and report that
   cluster's share of customers and its share of revenue, and
   (c) propose one specific marketing action for each cluster.

## Part D — Limits of k-means

10. In the *Where k-means Fails* tab, for **each** of the two datasets, report the percentage of
    points k-means put in their true group, the WCSS of k-means' answer, and the WCSS of the true
    groups. What does comparing the two WCSS values tell you about *why* k-means fails on these
    datasets?

## Part E — Another application

11. In the *Bonus: Photo Compression* tab, with the coffee photo (k-means++, seed 0), report the
    bits per pixel and the uncompressed size for **k = 4, 16, and 32**, along with the original's
    size. What is the smallest k at which the photo still looks acceptable to you, and why?

12. Describe **one other real-world use of k-means** (not customers or photos). What would each data
    point be, which features would you cluster on, how would you choose k, and what would you do
    with the clusters once you had them?

---
# References:
- [Streamlit documentation](https://docs.streamlit.io/)
- [Arthur & Vassilvitskii (2007), "k-means++: The Advantages of Careful Seeding"](https://theory.stanford.edu/~sergei/papers/kMeansPP-soda.pdf)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
