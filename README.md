# Executive KPI Studio

# Refactor Campaign Studio: Top Executive KPI Ribbon, Governed Audience Selectors, and Phase 1 Customer Output Table

Please update the Farmatodo Promotion Intelligence Studio workspace (`src/routes/index.tsx` and `src/components/layout/AppShell.tsx`) with the following updates requested by project leadership (Sourabh & Srashti).

---

### 1. Top Executive KPI Metric Ribbon (Direct Leadership Metrics)

Place a responsive, horizontal executive KPI ribbon across the full width directly above the main table.

The strip must prominently feature the exact metrics requested by Sourabh Agarwal and Srashti Pathak, with positive/negative trend pills and context tooltips:

1. **Incremental Revenue** (Sourabh requirement)

   - Value: `$1.24M` (or dynamically computed from selected table rows)

   - Trend / Delta: `+17.3%`

   - Subtitle: `Incremental revenue uplift generated`

2. **Incremental Units** (Sourabh requirement)

   - Value: `30.7K units`

   - Trend / Delta: `+15.4%`

   - Subtitle: `Net units above organic baseline`

3. **Customer Targeted Count** (Sourabh requirement)

   - Value: `67,460`

   - Trend / Delta: `+8.2%`

   - Subtitle: `Eligible campaign cohort size`

4. **True Promo ROI** (Sourabh requirement)

   - Value: `186%` (or `2.86x`)

   - Trend / Delta: `+12.1%`

   - Subtitle: `NIM / Total Promo Investment`

5. **Redemption Rate** (Srashti requirement)

   - Value: `28.4%` (historical benchmark: 15% - 35%)

   - Trend / Delta: `+4.5%`

   - Subtitle: `Coupon / offer redemptions`

6. **Audience Reached** (Srashti requirement)

   - Value: `53,960`

   - Trend / Delta: `80.0% of targeted`

   - Subtitle: `Total unique delivered reach`

7. **Net Incremental Margin (NIM)**

   - Value: `$126.2K`

   - Trend / Delta: `+17.3%`

   - Subtitle: `Net profit after pull-forward & cannibalization`

8. **Discount Efficiency Ratio (DER)**

   - Value: `1.41x`

   - Badge: `Target > 1.5x`

   - Subtitle: `Incremental revenue per $ discount spent`

---

### 2. Vertical 1: Governed Audience Type & Multi-Cluster Picker

In `src/routes/index.tsx` (Vertical 1 - Inputs):

1. **Add "Audience Type" Dropdown** (Blueprint Section 4.2):

   - Label: `AUDIENCE TYPE`

   - Options:

     - `Personalized Segment` (default)

     - `Mass / General`

     - `Reactivation`

     - `Cyclical Replenishment (RX)`

2. **Convert "Behavioral Segment" into a Multi-Select Component**:

   - Multi-select badges with checkboxes for the 7 production clusters:

     - `[x] Cluster 1 (A) — Champions / High Frequency`

     - `[x] Cluster 2 (B) — Loyalists / Category Explorers`

     - `[x] Cluster 3 (C) — Promising / Growth`

     - `[x] Cluster 4 (D) — At Risk / Price Sensitive`

     - `[x] Cluster 5 (E) — Reactivation / Lapsed`

     - `[x] Cluster 6 (F) — Replenishment / High Habit`

     - `[x] Cluster 7 (G) — Low Engagement / Occasional Basket`

   - Provide a "Select All / Clear All" quick action.

---

### 3. Vertical 2: Phase 1 Customer Output Table

Replace the current product-centric table with the customer-centric schema from Blueprint Section 4.5:

- **Table Columns**:

  1. `Campaign Name & ID` (e.g., "Mid-Year · AWARE-2025-VIT")

  2. `Customer ID` (e.g., `CUST-884210`)

  3. `Audience Segment` (e.g., `personalized_segment`, `rx_replenishment`)

  4. `Behavioral Cluster` (e.g., `Cluster 1 — Champions`)

  5. `Prime Status` (`Prime` vs `Non-Prime` badge)

  6. `Product Code` (e.g., `SKU-00012 · Rexona 012`)

  7. `Recommended Regular %` (e.g., `15%`)

  8. `Recommended Prime %` (e.g., `20%`)

  9. `Recommended Mechanic` (e.g., `pct_discount`, `coupon`)

  10. `Est. Incremental Units` (e.g., `+420.2`)

  11. `Est. Discount Cost` (e.g., `$6,118`)

  12. `Constraint Flags` (e.g., `invima_cap_30%`, `brand_price_floor`)

  13. `Decision & Action` (`YES` / `NO OFFER` status pill + `[Override]` button)

---

### 4. Remove Visualizations & Simplify Vertical 3

In `src/routes/index.tsx`:

- **REMOVE** the `WaterfallChart` panel ("Promotional Profit Build Waterfall").

- **REMOVE** the CATE Breakdown box and dose-response curve.

- Retain an **Executive Summary & Decision Hub** containing:

  - Active Campaign & Cohort summary card.

  - MLflow audit metadata badge (`run_8f29a`, model `causal-dml-v2.7`).

  - Action buttons: `[Override Recommendation]` and `[Export to RMS / Approve Campaign]`.

---

### 5. Top Navigation: Add 5th Tab "Analytics" (`src/routes/analytics.tsx`)

1. In `src/components/layout/AppShell.tsx`:

   - Add `Analytics` (`/analytics`) as the 2nd tab in the top navigation.

2. Build `src/routes/analytics.tsx` showing historical data and current promotional telemetry:

   - **Ongoing Campaigns Grid**: Active campaigns running across channels with dates and current discount depths.

   - **"Colour by Region" Regional Breakdown**: Cards comparing **Bogotá**, **Medellín**, **Cali**, and **Caracas/Maracaibo**:

     - Baseline velocity vs. active promotional run-rate.

     - Average discount depth applied.

     - Regulatory jurisdiction badge (INVIMA 30% cap vs. SUNDDE 25% cap).

 And i have shared you two screen shot of the page, so what we have tio do one thing more is that we have the user selection part will be in it correct position but the tabs which are showing the Net incremnetal discount efficiency and all will be at top and should be sequentially just like how i have shared the screen shot . and we have to remove the Nim from that tabs . And we have to make only one tab which will be campaign type like we have to change the name of the Campagin to campagin type and remove the original campaign type , we will just keep that sleection.


this was the working cdoe which i was doing with lovable with different account but the kimit got exceed . SO it has done much work but i want to confirm that is it done ? and we have to remove few thing from this which i have attached the screen shot .

i have also connect the current UI structure . So please consider that also . and give me final UI

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/d937a6b9-34af-4ddc-abb4-a265ad9e1cbb).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
