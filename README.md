VoltRelay: Battery-Swap Network Data Analytics & Predictive Modeling
🚀 Project Overview
VoltRelay operates an EV battery-swap network for 2-wheeler and 3-wheeler vehicles across 6 major Indian cities (Bengaluru, Delhi NCR, Hyderabad, Mumbai, Pune, and Jaipur). This project serves as the end-to-end master analytics pipeline for the VoltRelay Data Analytics Hackathon, diagnosing operational bottlenecks, understanding rider behavior, uncovering churn drivers, and building predictive models to drive network expansion and service reliability.

🛠️ Architecture & Pipeline
The pipeline follows a strict, immutable data-flow architecture where raw source files are never mutated, and all cleaning steps generate isolated, audited output datasets:

Raw Data
⟶
Audit
⟶
Clean
⟶
EDA
⟶
RFM Analysis
⟶
Observations
⟶
Churn Analysis
⟶
Model Training
⟶
Recommendations
Raw Data⟶Audit⟶Clean⟶EDA⟶RFM Analysis⟶Observations⟶Churn Analysis⟶Model Training⟶Recommendations
Master Notebook Progress
Step 1: Problem Understanding — Completed (
✓
✓)

Step 2: Data Loading & Verification — Completed (
✓
✓)

Step 3: Data Inspection & Quality Audit — Completed (
✓
✓)

Step 4: Data Cleaning — Completed (
✓
✓)

Step 5: Step 3 & 4 Validation — Completed (
✓
✓)

Step 6: Exploratory Data Analysis (EDA) — Completed (
✓
✓)

Step 7: RFM (Recency, Frequency, Monetary) Analysis — Completed (
✓
✓)

Step 8: Observations, Insights & Hypotheses — Completed (
✓
✓)

Step 9: Churn Analysis — Completed (
✓
✓)

Steps 10–13: Model Training, Evaluation & Business Recommendations — In Progress / Pending

📂 Dataset Inventory & Known Quality Issues
The project integrates 8 core relational datasets:

swap_events.csv (3,877,013 rows 
×
× 22 cols) — Individual battery swap transactions.

station_hourly_status.csv (1,487,712 rows 
×
× 14 cols) — Hourly telemetry, temperature, and grid load per station.

riders.csv (20,000 rows 
×
× 12 cols) — Rider demographics, vehicle class, home zone, and plan types.

batteries.csv (6,500 rows 
×
× 13 cols) — Battery health and lifecycle metrics.

support_tickets.csv (44,000 rows 
×
× 12 cols) — Customer service logs and complaint categories.

stations.csv (152 rows 
×
× 22 cols) — Station locations, capacity, and infrastructure specs.

city_daily_context.csv (3,282 rows 
×
× 12 cols) — External daily factors (weather, traffic, city-level metrics).

fleet_partners.csv (12 rows 
×
× 12 cols) — B2B partner details and contract structures.

Key Data Anomalies Handled in Cleaning:
UTC Offset Bug: Firmware v3.2.0 records between 2025-03-10 and 2025-04-14 stored timestamps 
∼
∼5 hours 30 minutes behind local Indian Standard Time (IST).

Physical Impossibilities: Filtered out negative km_since_last_swap entries (7,814 rows) and State of Charge (SOC) / State of Health (SOH) telemetry outliers outside the 
0
–
100
%
0–100% bounds.

Sync Duplicates: Removed near-duplicate swap events occurring within a 60-second window resulting from offline batch syncs.

💡 Core Business Questions Addressed
Station Performance: Pinpointing underperforming cities and stations by evaluating queue wait times, uptime, and grid load.

Rider Churn: Identifying behavioral red flags and high-risk segments to reduce attrition.

Reliability & Satisfaction: Quantifying how battery health (SOH) and swap reliability impact customer satisfaction and support ticket volumes.

Pricing & Contracts: Evaluating whether current tariff codes and partner contract structures align with real-world usage patterns.

Operational Uptime: Recommending telemetry and maintenance interventions to minimize outage minutes.

Network Expansion: Prioritizing high-demand zones for upcoming station deployments.

💻 Tech Stack & Libraries
Language: Python 3.13+

Core Libraries: Pandas (v2.2.3), NumPy (v2.1.3)

Visualization: Matplotlib, Seaborn

Environment: Google Colab / Jupyter Notebooks with Google Drive integration
