## Day 8: Build Your First AI-Powered Dashboard

Today's task is to create interactive dashboard. Claude Artifacts allow us to generate fully interactive applications instead of simple text outputs. By combining prompts, reasoning, design instructions, and structured requirements, Claude can build dashboards, tools, calculators, visualizations, and complete HTML applications.

### Prompt
>
    Act as a Senior Data Analyst, Environmental Researcher, UX Designer, and Frontend Dashboard Developer.

    Create a Claude Artifact called:
    🌍 Personal Environmental Health Analyzer
    
    DATA RULES
    
    If a dataset is provided, use it. If no dataset is provided, automatically search the web for the latest AQI and water-quality data for New Delhi, India. If location is unavailable, ask for the city name first. Use the most recent available data, cite sources, clean the data, handle missing values, and validate quality before analysis.
    
    ANALYSIS
    
    Generate: cleanest city, most polluted city, highest AQI city, lowest AQI city, average AQI, number of cities analyzed, trends, anomalies, most surprising observation, executive summary.
    
    INTERACTIVE DASHBOARD
    
    Create a fully interactive Claude Artifact with:
    
    📊 Key Metrics: average AQI, highest AQI city, lowest AQI city, number of cities analyzed, environmental health score.
    
    📈 Visualizations: AQI comparison chart, PM2.5 comparison chart, PM10 comparison chart, city ranking chart, AQI distribution chart.
    
    🎛 Interactive Filters: city selector, AQI range filter, pollutant selector, health-risk filter, date filter (if available), city comparison mode.
    
    📋 City Detail Cards: AQI, PM2.5, PM10, air-quality category, health score, water-quality score.
    
    🚦 AQI Categories: Good (Green), Satisfactory (Light Green), Moderate (Yellow), Poor (Orange), Very Poor (Red), Severe (Dark Red).
    
    ENVIRONMENTAL HEALTH ANALYSIS
    
    For the selected city explain AQI impact on lungs, sleep, energy levels, exercise performance, long-term health, and water-quality impact on hair fall, hair dryness, scalp health, skin dryness, acne, and sensitive skin.
    
    Use risk indicators: 🟢 Low, 🟡 Moderate, 🔴 High.
    
    PERSONAL REPORT CARD
    
    Generate an Environmental Health Score (0–100) with breakdowns for Air Quality Score, Water Quality Score, and Overall Environmental Score.
    
    Assign grades for Air Quality (A–F), Water Quality (A–F), Hair Risk, and Skin Risk.
    
    INSIGHTS PANEL
    
    Include: top 3 cleanest cities, top 3 most polluted cities, biggest anomaly, most surprising observation, recommended actions.
    
    PERSONALIZED RECOMMENDATIONS
    
    Provide: daily actions, indoor air improvements, outdoor activity guidance, hair-care recommendations, skin-care recommendations, water-quality improvement suggestions.
    
    DESIGN
    
    Modern, professional, mobile responsive, dark theme, smooth animations, premium UI, clean typography, dashboard-style layout, highly visual, colourful, LinkedIn-shareable.
    
    OUTPUT
    
    Generate a complete downloadable HTML application that is fully responsive and ready to save as index.html.
    
    IMPORTANT
    
    Do not provide code snippets. Create a complete interactive Claude Artifact with working charts, filters, cards, insights, report cards, and dashboards that users can interact with directly.
>

### Response
I'll start by getting the latest AQI and water-quality data for New Delhi, then build the dashboard.Let me get water quality data and a few comparison cities for context.I have enough data. Let me get a few comparison Indian cities' AQI to enable the multi-city analysis, then build.I have solid, current data. Let me read the frontend-design skill, then build the complete HTML application.Now I'll build the complete dashboard with all the data I've gathered.Let me verify it's valid and self-contained, then move it to outputs.Done. Here's your **🌍 Personal Environmental Health Analyzer** - a complete, self-contained `index.html` you can save and open in any browser.

**Data used (live, retrieved 7 Jun 2026):** No dataset was attached, so I pulled the most recent AQI/PM readings for New Delhi plus 8 comparison Indian cities, and city water-quality (TDS/hardness) ranges. Key current figures: Delhi's real-time AQI is 100 (Moderate), with New Delhi PM2.5 ~74.81µg/m³ and PM10 ~176.05µg/m³. Across cities: Kolkata 139, New Delhi 117, Hyderabad 80, Chennai 79, Bangalore 75, Pune 69, Mumbai 60, with Lucknow around 152. Water: Delhi runs 400 – 800ppm TDS, Punjab/Rajasthan often exceed 1000ppm, while the ideal drinking range is 150 – 300mg/L and BIS allows up to 500.

**What's inside, all interactive:**
- **Key metrics**: average AQI, highest/lowest AQI city, cities analyzed, and a live environmental health-score ring for the selected city.
- **5 charts**: AQI comparison, PM2.5, PM10, cleanliness ranking, and category distribution (rebuild on every filter change).
- **Filters**: city selector, AQI range slider, pollutant focus, 🟢🟡🔴 health-risk filter, and single-vs-compare-all mode.
- **City cards**: tap any card to drive the health analysis, report card, and recommendations.
- **Health analysis**: AQI impact on lungs, sleep, energy, exercise, long-term health + water impact on hair fall, dryness, scalp, skin, acne, sensitive skin, each with a risk indicator.
- **Report card**: 0 – 100 score with Air/Water/Overall breakdown and A–F grades for air, water, hair, and skin.
- **Insights**: top 3 cleanest/most polluted, the biggest anomaly (Jaipur: decent air, worst water), the surprise (Lucknow currently beating Delhi for worst air), and recommended actions.
- **Personalized recommendations** + executive summary.

The most surprising finding: in this June pre-monsoon snapshot, Delhi isn't even the worst-air city — and water quality, not air, is the quieter driver of everyday hair and skin complaints. One note on accuracy: live AQI fluctuates hourly and the water TDS figures are typical city ranges, not single-point measurements.

## Key Learnings 

### Dashboard
I played around with this dashboard and there are multiple things that impressed me.

**1. Clean Dashbaord** Dashboard itself is very clean, looks professional and very responsive.
[Personal Environmental Health Analyzer](index.html)

**2. Landing & Key Metrics**
Default state, New Delhi selected. Average AQI 93 (Satisfactory) across all 9 cities; Lucknow flagged as highest (152), Mumbai lowest (58); New Delhi health score 53/100, Grade D. [landing_key_metrics](landing_key_metrics.png)

**3. All Visualizations**
All five charts at once: AQI comparison (bars colored by category), PM2.5, PM10, city cleanliness ranking, and the AQI category distribution doughnut. [all_visualizations](all_visualizations.png)

**4. Lucknow Health Analysis**
The surprise finding — Lucknow at AQI 152 is the most polluted city in the set, worse than New Delhi. Red High-risk badges across lungs, sleep, energy, and exercise. [lucknow_health_analysis](lucknow_health_analysis.png)

**5. Lucknow Report Card**
Low overall environmental score with A–F grades for Air Quality, Water Quality, Hair risk, and Skin risk. [lucknow_report_card](lucknow_report_card.png)

**6. Jaipur Water Anomaly**
The key anomaly — only Moderate air, but the worst water in the set (~900ppm TDS). Hair/skin panel shows High risk despite the comparatively decent AQI. [jaipur_water_anomaly](jaipur_water_anomaly.png)

**7. Mumbai Clean Report**
Contrast case — one of the cleanest cities, score 81/100, Grade B, strong across air, water, hair, and skin. [mumbai_clean_report](mumbai_clean_report.png)

**8. AQI Filter Applied**
AQI range capped at 100. Metrics recompute live: Cities Analyzed drops from 9 to 5, average AQI falls to 66, and Hyderabad becomes the new highest-AQI city. [aqi_filter_applied](aqi_filter_applied.png)

**9. Filtered City Cards**
After the AQI≤100 filter — Delhi, Kolkata, Jaipur, and Lucknow are removed. Remaining cards show AQI, PM2.5/PM10, air & water scores, and risk badges. [filtered_city_cards](filtered_city_cards.png)

**10. High-Risk Filter Charts**
Health-risk filter set to High only. Charts redraw to just the dangerous-air cities (Kolkata, Jaipur, Lucknow); the doughnut collapses to the worst categories.

**11. Insights Panel**
Top-3 cleanest vs Top-3 most-polluted cities, plus the explicit Anomaly, Most-Surprising observation, and Recommended-actions callouts.

### On Working with Claude as a builder

- **I learned to treat the AI as a capable collaborator, not a vending machine.** The quality of what I got back was directly proportional to the clarity of intent I gave. A vague ask produces generic output; a specific brief — data rules, sections, design tone, fallback behavior — produces something usable. Prompting is really requirements-writing in disguise.

- **I saw that real outputs come from real tooling, not illusion.** The screenshots weren't faked or "described" — they were produced by actually launching the dashboard in a browser and driving it. That distinction matters: trustworthy AI work is verifiable, reproducible, and traceable back to a concrete process.

- **I learned that obstacles are part of the process, not a failure of it.** Midway through, the headless browser couldn't load the charting library because of a network restriction. The work didn't stop — it adapted by bundling the library locally. My takeaway: judge an AI workflow by how it handles friction, not by whether friction appears.

### On data and analysis

- **I now understand that data is never clean on arrival.** The same city showed six different air-quality readings across sources, depending on station, hour, and measurement scale. The real skill wasn't fetching numbers — it was *reconciling* them and choosing a defensible standard. Analysis begins where the raw data ends.

- **I learned to value honesty about uncertainty over false precision.** The water-quality figures were ranges, not exact measurements, and that was stated plainly rather than disguised as certainty. Credible analysis distinguishes what it knows from what it estimates.

- **I saw how raw numbers become meaning through logic.** A figure like "TDS 650" is inert until a scoring rule turns it into "high hair-fall risk." The interpretive layer — the formulas and thresholds — is where analytical value actually lives, and it's the part a casual observer never sees.

### On insight and communication

- **I learned that the best insight is the non-obvious one.** The headline wasn't "Delhi has bad air" — everyone knows that. It was that another city quietly had worse air, and that a city with decent air had the worst *water*. Surfacing what a naive ranking would miss is the difference between a report and an insight.

- **I came to see design as a functional decision, not decoration.** Color-coding by severity, live-recomputing filters, a clear visual hierarchy — these weren't aesthetic flourishes; they made the data legible and the tool trustworthy.

### The meta-learning, if I could keep only one

- **I learned to separate the human judgment from the machine execution.** The AI can fetch, compute, render, and iterate at speed — but deciding *what's worth measuring, which trade-offs are acceptable, and what the result actually means* remained mine to own. The most valuable position in an AI workflow isn't operating the tool; it's directing it and validating its output.