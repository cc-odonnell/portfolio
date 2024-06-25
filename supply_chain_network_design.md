How Supply Chain Strategy Can Tackle Infectious Diseases
Where should NGOs and government agencies locate medical centers for the rapid treatment of Ebola patients? Replace “medical centers and patients” with “stores and customers” or “manufacturing plants and warehouses” and this becomes a typical look at network topology and design. 

**Visualizations Created with Tableau** 
*Note: Data taken from publicly available sources.*

When the Ebola virus swept through West Africa from April 2014 to March 2015, the urgency to effectively treat patients was paramount. Understanding where to place medical centers for rapid treatment became a critical task for NGOs and government agencies. By applying a strategic supply chain approach—similar to locating stores for customers or positioning manufacturing plants near warehouses—we can significantly improve healthcare outcomes.

**Ebola's Spread in West Africa**

The Ebola outbreak reached its zenith in December 2014, with Liberia and Sierra Leone bearing the brunt. Liberia saw two distinct waves in September and December, while Guinea experienced a steady stream of cases, ranking third in severity.



**Medical Centers Status**

By November 2014, Western Africa had 50 functional medical centers, 54 pending, and 4 closed. These centers were densely clustered in Sierra Leone and Liberia, reflecting the regions' high case counts. 




**A Strategic Approach to Supply Chain**

To optimize the placement of medical centers, a linear programming model was employed. The goal was to minimize the travel distance between patients and medical centers. This model revealed that strategically redistributing existing resources could dramatically cut travel distances for patients by over 1,000 people-miles. In Sierra Leone, targeting outlying areas like Kono and Jui could capture an additional 53% of cases.

**Conclusion**

This strategic approach underscores the power of supply chain optimization in healthcare. By applying these principles, NGOs and governments can enhance their response to infectious diseases, ensuring rapid and efficient treatment for affected populations. Through data-driven strategies and innovative models, we can transform healthcare delivery and save lives.


**Methodology**

A sample of the R code is available here [link]. Note that data cleaning steps and additional LP runs were omitted for brevity. 

To analyze the best supply chain strategy, I ran an LP model to minimize the distance between MCs and cases, using weighted miles (miles as the crow flies multiplied by number of cases). We assume each MC can handle infinite capacity. By doing this, I focused on how to minimize the distance traveled by infected people; perhaps going from a rural village along poor infrastructure to a central MC location. The MC datafile was deduped by location, for a total of 28 unique locations for existing MCs and 47 unique locations for both existing and pending MCs.

Running the model for the existing 28 MCs resulted in a total of ~3500 miles to reach all Ebola cases. Allowing the model to select any 28 locations from the full list of 47 possible, resulted in a total of ~2500 miles, a substantive reduction. For the final model run, I allowed any number of MCs from the full list to be selected. Surprisingly, the model chose only 32 of the total possible locations, for a total of ~2400 miles, only a 100 mile reduction from the previous iteration. This suggests that by simply shifting existing resources from current locations to better locations, medical responders could drastically improve outcomes. 

