# Research Question

A key component of record linkage is accuracy assessment — the process of manually verifying and validating matched pairs to further refine linkage parameters and increase its overall effectiveness. This process however is time-consuming and impractical when applied to large data sources where millions of records must be linked. Additionally, it is potentially biased as the ground truth used is often the reviewer’s intuition. This problem is especially more pronounced in the case of probabilistic linkage, as there is no gold standard as to which metric is the best – sensitivity specificity and positive predictive value. 

We have seen how large the patents and federal grants datasets are, and even more so if it is accumulated across the years. It is also reasonable to think that there will be many entities that are registered in multiple different names and locations. Such problems make it hard for data practitioners working on the two data to utilize deterministic linkage and they often need to resort to probabilistic linkage, exposing them to the above-mentioned problems of accuracy assessment.

With this context in mind, for this project, I will try to propose a different method of accuracy evaluation that is more objective and efficient. Drawing from Pita, Jesus, Reis and Barreto’s paper, I plan to train a few supervised machine learning models to assess the accuracy of probabilistic linkage.

# Repository Structure

	.
	|-- Code                             # Python codes
	|-- Data                             # Data files
	|   |-- Clean                        # Cleaned data for analysis
	|   |-- Raw                          # Raw data
	|-- Figures                          # Figures and images


# Expected Impact

 1. Propose an alternative to manual accuracy assessment based on ML models that improves efficiency and accuracy
 2. Cost reduction for USPTO and other related organizations on Data collection and quality assurance stages
 3. Enable potential researches for smaller organizations, members of civil society and academics that were hindered by lack of resources and time because of lengthy and labor-intensive data linkage and accuracy assessment stages

# Data Sources

 1. [Patents data 2010 ~ 2018](https://www.patentsview.org/)
  2. [Federal Grants data 2010 ~ 2018](https://developer.spotify.com/documentation/web-api/)
  
# Analysis Plan

 * Query API to collect data
 * Clean and transform data to retain necessary features
 * Deterministically link a subset of patents and grants dataset to create a test data
 * Probabilistically link the rest of the data that cannot be deterministically linked
 * Train ML models on the data that has been probabilistically linked
 * Evaluate the models and select the best performing model
 * Test the model using the test set

# Required Skill
The dataset involved is quite large and it may be inefficient to run everything on my local machine. I may resort to Dumbo, a Hadoop cluster offered through NYU High Performance Computing.