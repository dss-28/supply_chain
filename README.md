🌍 Carbon-Aware Supply Chain Optimization System
An end-to-end decision support system that simulates, optimizes, and stress-tests a supply chain under economic and climate constraints.
This project goes beyond model building and focuses on system-level trade-offs between cost, service levels, and carbon emissions.
________________________________________
🎯 Problem Statement
Modern supply chains face three simultaneous pressures:
•	Rising operational costs
•	Volatile demand and fuel prices
•	Increasing regulatory and ESG pressure to reduce carbon emissions
Most ML projects stop at prediction.
This system answers “What should we do under uncertainty and policy shocks?”
________________________________________
🧠 System Architecture
Supply Chain Simulator
        ↓
Demand Forecasting (P50 / P90)
        ↓
Inventory Optimization (LP)
        ↓
Routing Optimization (LP)
        ↓
Carbon Accounting Engine
        ↓
Scenario & Policy Simulation
        ↓
Explainability & Insights
________________________________________
✅ Key Modules
1️⃣ Supply Chain Simulator
•	Synthetic digital twin (warehouses → cities)
•	Simulates demand, shipping, distance, cost, emissions
•	Output: logistics_simulated.csv
________________________________________
2️⃣ Demand Forecasting (Uncertainty-Aware)
•	Forecasts demand per city × day
•	Generates:
o	P50 (expected demand)
o	P90 (used for service-level safety stock)
•	Output: demand_forecast.csv
________________________________________
3️⃣ Inventory Optimization (Linear Programming)
•	Objective:
•	Minimize: Cost + λ·CO₂ + μ·Stockouts
•	Explicit service-level control using P90
•	Solver: CBC (PuLP)
•	Output: shipment_plan_realistic.csv
________________________________________
4️⃣ Routing & Transport Optimization
•	Optimized shipment flows from warehouses to cities
•	Distance-aware routing
•	Output: shipment_plan_routed.csv
________________________________________
5️⃣ Carbon Accounting Engine
•	Explicit CO₂ measurement (not just objective penalties)
•	Computes emissions:
o	Per warehouse
o	Per city
o	Per day
o	System-level totals
•	Output: carbon_report.csv
________________________________________
6️⃣ Scenario & Policy Simulation
Stress-tests the system under:
•	Baseline
•	Carbon Tax (₹50 / kg CO₂)
•	Fuel Price Shock (2×)
•	Demand Surge (1.5×)
Recomputes:
•	Total cost
•	Total emissions
Output: scenario_results.csv
________________________________________
7️⃣ Explainability & Insights
Compares scenarios against baseline:
•	% change in cost
•	% change in CO₂
•	Qualitative interpretation
Example insights:
•	Carbon tax → cost explodes, emissions unchanged
•	Demand growth → emissions rise without cost increase
•	Fuel shock → cost and emissions both double
Output: scenario_explainability.csv
________________________________________
📊 Sample Results
Scenario	Δ Cost	Δ CO₂	Insight
Carbon Tax	+900%	0%	Policy cost burden
Demand Surge	0%	+50%	Growth-driven emissions risk
Fuel Shock	+100%	+100%	Energy price risk
________________________________________
🧠 Why This Project Is Different
•	Not a notebook — a system
•	Combines:
o	ML forecasting
o	Operations research
o	ESG / climate accounting
•	Focuses on decision-making, not just prediction
•	Designed like a real internal analytics platform
________________________________________
🏢 Use Cases
•	Supply chain analytics
•	Climate / ESG decision support
•	Operations optimization
•	Policy stress testing
________________________________________
🚀 Tech Stack
•	Python, Pandas
•	PuLP (Linear Programming)
•	Optimization & Simulation
•	System design principles
________________________________________
📌 Status
Core system complete and stable.
Future extensions: re-optimization under carbon tax, dashboards.
________________________________________
