# Analysis of Corporate Publications in the Semiconductor Field

This repository contains a Python-based analysis of corporate academic publications in the semiconductor industry from 1950 to the present day. The primary data source is the [OpenAlex API](https://docs.openalex.org/), supplemented with organizational hierarchy data from the [Research Organization Registry (ROR)](https://ror.org/).

## Methodology

The analysis is conducted via the Jupyter Notebook `Code/semiconductor_company_publications.ipynb`. The core methodology involves the following steps:

1.  **Data Collection**: The script queries the OpenAlex API for scholarly works related to a curated list of semiconductor topics. The search is filtered to include only publications affiliated with institutions classified as "company".

2.  **Parent Company Resolution**: A key feature of this analysis is the consolidation of publications under their ultimate parent organization. For each publishing institution, the script uses its Research Organization Registry (ROR) ID to traverse the organizational hierarchy via the ROR API. This process identifies the top-level parent company, ensuring that publications from all subsidiaries are correctly attributed. A name-matching fallback is used for institutions lacking a ROR ID.

3.  **Data Aggregation**: The collected data is aggregated in two primary ways:
    *   **By Region and Year**: Publication counts are grouped by the geographical region of the parent company's headquarters (US, Asia, Europe, Rest of World) for each year.
    *   **By Parent Company and Decade**: Publication counts are summed for each parent company over each decade to identify the most prolific publishers over time.

## Output

The notebook generates several visualizations to present the findings:

1.  **Regional Publication Trends**: A line chart illustrating the volume of publications from each major geographical region over time.
2.  **Regional Publication Share**: A series of pie charts showing the percentage share of publications from each region for each decade.
3.  **Top 50 Publishers by Decade**: A series of bar charts ranking the top 50 parent companies by their total publication output for each decade.

The resulting data is also available for further analysis.