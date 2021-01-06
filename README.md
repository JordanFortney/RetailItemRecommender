# Retail Item Recommender for Walmart 24 Hour Project

### Introduction
During my data science diploma at BrainStation, we were grouped with other students from the three other diploma programs and surprised with a business challenge to answer and design a solution around. The context of the challenge was based around the global pandemic altering consumer behaviours, online shopping (eCommerce) experiencing unprecedented growth and disruption. The specific question we were tasked in answering was "What data-driven digital experiences can we deliver to help customers to save money and live better?". We were given 24 hours to analyze, plan, and execute a solution which we then presented to members of the Data Science team at Walmart. 

Our solution was to design and build a chatbot for the online and mobile sites that will provide customer service and recommendations to the customers based on what is placed in their cart. My UX teammates designed the layout, style, and functionality of the chatbot. The developers on our team then wrote the code to make it work. Our marketing student put together the slides and sales pitch for our presentation. As the data science representative for our group, I was responsible for providing basic statistics about the data we were given, creating visualizations, and writing the recommender system for the chatbot. 

### Data
We were given mostly pre-cleaned retail sales data for October and November of 2019 in .csv format. This data did contain some NaN values for the product brand but they were not relevant to the basket analysis so they were left in place. They were replaced with an “other” tag for the EDA and statistical analysis done in another notebook for this project. I did take a 0.8% sample of the data to build and test the function because it was otherwise too large for my personal PC. 

### Methodology
I began by grouping the product IDs by user session. This gave me a list of what items were interacted with during the same session. We did talk about just linking purchased items but there was much less data with those stipulations so I decided to group items that were also simply viewed in the same session. I then encoded all the values of the grouped lists so I could apply the occurrence percentages from the encoded data to the algorithm later on. I then used the FP-Growth algorithm to extract frequent itemsets that can be applied to association rule learning. It formalizes the rough calculation we did earlier to find the support of each itemset. Association rules were then applied to calculate the lift (how much more the two products interacted together than we would have expected if they were statistically independent) which was the main metric I used to evaluate the itemsets.

### Final Function
Once the association rules were set I was able to write a function that took a random item from the “basket” of the user and recommend 2 items that were also viewed or purchased by other customers. For privacy reasons, Walmart only provided us with a product ID and not the actual name of the product so the results were not as interesting as I would have liked but there is no difference between the product ID and the actual name of the product. 

### Next Steps
I’ve decided to not alter or improve on this project going forward. I want it to show the work I can produce under the circumstances of a short timeline and a surprise issue that needed a solution in tandem with multiple departments working towards a common goal. 


