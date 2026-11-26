# Google Play Store Apps — Exploratory Data Analysis (`appinsight`)

A structured Exploratory Data Analysis (EDA) case study of the **Google Play Store** (`googleplaystore.csv`), organized into a complete **Case Study Document**, **Solution Guide**, and **Additional Resources**.

---

## 1. Case Study Overview & Problem Statement

With thousands of competing apps across every category on the **Google Play Store**, developers and product strategists must understand what separates high-install, top-rated applications from low-traction listings. Using cleaned Play Store listing data (`9,659` unique apps across `33` categories), this project investigates:
* Which categories and genres capture the highest app volume versus the highest user install demand.
* How monetization (`Free` vs. `Paid`) and price tiers impact user ratings and download volume.
* How user engagement (`Reviews`), app package size (`Size`), target audience (`Content Rating`), and maintenance recency (`Last Updated`) relate to app performance.

---

## 2. Data Dictionary

* **Dataset:** `googleplaystore.csv` (`10,841` raw records → `9,659` deduplicated unique apps across `13` attributes)

| Feature | Type | Description |
|---|---|---|
| `App` | Categorical | Application title |
| `Category` | Categorical | Primary Play Store category (`33` unique categories) |
| `Rating` | Numeric | User rating score (`1.0` to `5.0`) |
| `Reviews` | Numeric | Total count of user reviews |
| `Size` | Numeric | Application file size standardized in Megabytes (`MB`) |
| `Installs` | Numeric | Cumulative download count (`0` to `1,000,000,000+`) |
| `Type` | Categorical | App pricing model (`Free` or `Paid`) |
| `Price` | Numeric | Retail price in USD (`0.0` for free apps) |
| `Content Rating` | Categorical | Age suitability classification (`Everyone`, `Teen`, `Mature 17+`, etc.) |
| `Genres` | Categorical | Specific sub-genre classification |
| `Last Updated` | Datetime | Date of the most recent Play Store release |
| `Current Ver` | Categorical | Current release version string |
| `Android Ver` | Categorical | Minimum Android OS version requirement |

---

## 3. Solution Guide Summary

### Basic-Level Insights
* **Top Categories by App Count:** **Family**, **Game**, and **Tools** account for the largest share of published applications on the Play Store.
* **Monetization Split:** Over **92%** of apps are **Free**, while less than **8%** follow a **Paid** upfront model.
* **Rating Distribution:** App ratings are left-skewed with a high central tendency around **4.2–4.3 out of 5.0**, showing that active Play Store apps generally maintain strong baseline satisfaction.
* **Content Rating Breakdown:** **Everyone** represents the vast majority of listings (~82%), followed by **Teen** (~11%) and **Mature 17+** (~4%).

### Medium-Level Insights
* **Installs vs. App Supply:** While **Family** has the most app listings, **Communication**, **Social**, **Video Players**, and **Game** generate the highest total and average installs per app.
* **Free vs. Paid Performance:** **Paid** apps show a slightly higher median rating than **Free** apps (due to fewer ad-driven complaints), but **Free** apps capture the overwhelming majority of total downloads.
* **Reviews & Installs Relationship:** Strong positive correlation exists between `Reviews` and `Installs`—confirming review volume as a primary proxy for active user base size.

### Advanced-Level Insights
* **Multi-Factor Drivers of Success:** High-install apps combine a **Free** entry model (supported by in-app monetization), frequent updates (`Last Updated`), broad `Everyone` content accessibility, and active review engagement.
* **Pricing Sweet Spot:** Most successful paid apps cluster under **$10**, whereas outlier luxury/novelty apps ($200+) generate negligible install volume.
* **Strategic Recommendations:** Launch new consumer apps under a **Free / Freemium** model, prioritize regular update cycles to sustain Play Store ranking and ratings, and target high-demand categories (`Tools`, `Productivity`, `Communication`, `Game`) with clear sub-genre differentiation.

---

## 4. Repository Structure

```text
appinsight/
├── googleplaystore.csv         # Source dataset
├── appinsight_eda.ipynb        # Complete Jupyter Notebook (Case Study, Code, Visuals & Solution Guide)
└── README.md                   # Case Study Overview, Data Dictionary, Key Findings & Resources