---
layout: default
title: HW5 – Altair Visualizations
permalink: /hw5/
---

# HW5 – Two Views of the Same Dataset

<!-- Buttons -->
<div style="margin: 1rem 0; display:flex; gap:.5rem; flex-wrap:wrap;">
  <a href="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv" target="_blank" style="padding:.5rem .8rem; border:1px solid #ccc; border-radius:.4rem; text-decoration:none;">The Data</a>
 <a href="https://github.com/ntewodros/ntewodros.github.io/blob/main/python_notebooks/Workbook.ipynb" target="_blank" style="padding:.5rem .8rem; border:1px solid #ccc; border-radius:.4rem; text-decoration:none;">The Analysis</a>
</div>

## Plot 1: Count of Buildings by Construction Decade
<iframe src="/export/plot1_decade_counts.html" width="100%" height="420" style="border:none;"></iframe>

**What this shows:**  
This plot uses hisograms to visualize the distribution of construction decades for Illinois buildings. Outlier buildings without a proper decade are shown as from the 0s, with all others shown between the 1750s and 2020s as applicable. There is a distinct left skew in the graph, with construction rising in the 20th century, peaking in the 1970s, and drastically falling off in the 2010s.

**Design choices (encoding & color):**  
The x axis is ordinal with decade labels sorted chronologically and simple bar marks. The y axis is simply representing the count of buildings constructed. There is only one hue for the histograms to keep the focus on the time distribution. Tooltips are used to show exact metrics for different bars. 

**Transformations:**  
Data transformation was used to extract the values from the Year Constructed column of the data. The values were turned from strings ("1990s") to numerical values (1990). These were then bucketed by decade.

---

## Plot 2: Top Agencies (Filter by County/Status)
<iframe src="/export/plot2_top_agencies_interactive.html" width="100%" height="520" style="border:none;"></iframe>

**What this shows:**  
This plot uses horizontal bars to display the number of buildings in the Illinois inventory. Specifically, it prioritizes the top 15 agencies for each grouping. 

**Design choices (encoding & color):**  
The X-axis shows the number of buildings. The Y-axis shows the agency names. Color is all the same to prioritize viewing the size of bars next to each other.


**Transformations:**  
The transformation done here is sorting by the top-15 agencies and showing graphs by #1 Agency,  #2 Abandoned, In Progress, and In Use & #3 county.


**Interactivity:**  
Dropdown filters (County/Status) via Altair params bound to `<select>` inputs; helps focus on specific geographies/status categories.
