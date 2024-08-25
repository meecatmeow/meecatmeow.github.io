---
Layout: post
Author: Julie Chua
Title: "Applied Data Science Project Documentation"
Categories: ITD214
---

## Project Background
As a member of a support group, we aim to set up an online support system to improve emotional support and provide a sense of community and anonymity to those taking part and seeking help.
The online community allows individuals who feels lonely or socially isolated to connect with others experiencing similar challenges and share coping strategies.
By understanding user needs, preferences, and behaviours of the R/foreveralone community, we can optimize the platform's content to better meet their expectations. 
Ultimately, the goal is to create a positive and supportive online environment that fosters a strong sense of community and empowers users to effectively address their challenges. 
As a measurement of our goal we hope to see at least 20% positive sentiment expressed by users after setting up the online community.

S/N| Business Objectives   | Member In Charge              
-- | --------------------- | --------------------- 
1  | Identify distinct demographic groups within the r/ForeverAlone community to create social marketing strategy to increase public’s interest to join the community. | Julie    
2  | Uncover the primary topics discussed within the r/ForeverAlone community to gain insights into the specific challenges users face and determine what users hope to achieve through the online community. | Kendra 
3  | Determine the likelihood of depression in users based on their demographic and behavioural attributes | Ken
4  | Interpret the predominant emotions and overall sentiment expressed within the r/ForeverAlone community to understand the struggles and motivation of the users. | Jerry

## Project Timeline
![Project Timeline](https://github.com/user-attachments/assets/397561ec-046e-4169-bd18-70451354e29a)

## Work Accomplished
Business objectives 1 and 3 are using the same dataset, therefore common data pre-processing steps were used.

### Data Preparation
A. Common Data Pre-processing steps
- Load data
  - Use of head() and info() > special characters observed, there are two numeric datatypes
  - Use of boxplot for the two numeric datatypes > concentration of 20-25 for 'age' and outlier of 400+/600+ 'friends'
- Handle missing values
- Remove special characters
- Simplify 'race' through use of mapping
- Standardize 'pay_for_sex' through replacement
- Transform yes/no replies to boolean conversion of 1/0
- Create new column 'generation' through binning of 'age'
B.  Further Data Pre-processing steps to facilitate clustering model building
- Primary demographic features identified. Remove features related to behavior and psychoogical state
  - Left with 8 features: 'gender', 'sexuality, 'income', 'race', 'bodyweight', 'employment', 'edu_level_cleaned', and 'generation'
- Encoding categorical values to numerical values
  - All features identified are categorical, except for 'income' which is ordinal in nature
  - Label encoding map saved for referencing

### Model Building and Evaluation
1. Prior to building clustering model, perform elbow method to determine the optimal number of clusters
   - 4 clusters identified through elbow method graph plotted that showed the point where additional clusters no longer significantly reduced the within-cluster sum of squares, indicating diminishing returns on further increasing the number of clusters
2. To visualise the clusters easily, pair-plot was chosen as there are 8 features, which is quite a number to plot and examine. Having them plotted pair-wise allowed for a comprehensive view of pairwise relationships, making it easier to identify patterns and cluster separations
   - 3 features displayed clearer cluster formations, which guided our interpretation of the cluster profiles i.e. 'income', 'employment', edu_level_cleaned'
3. Determination of cluster centers in order to identify profiles
   - common characteristics emerged: male, straight, Caucasian

## Recommendation and Analysis
The analysis focused on understanding demographic patterns within the dataset using clustering techniques. By examining the clusters formed based on the demographic features, we identified distinct groups that could provide insights into different profiles. The clear separations seen in the pair-plots for 'income', 'employment', and 'edu_level_cleaned' suggest that these features play a significant role in defining the clusters.
Based on the clustering analysis, we recommend further exploring the relationships between these key demographic features and other variables that were initially removed, such as behavioral and psychological states. Understanding how these clusters differ in their behaviors or psychological traits could provide deeper insights and more targeted strategies for engagement or intervention.

Additionally, since the clusters showed strong patterns in specific demographic features, it may be beneficial to tailor services, communications, or products to these distinct groups. For example, customizing offerings based on 'income' or 'employment' status could enhance relevance and effectiveness for each identified cluster.

A social marketing proposal targeting straight Caucasian male, overwieght, Gen Z with low income is concepted as a possible strategy:

Scope               | Description
----------------------- | --------------------------------------
Platforms               | TikTok, Instagram, and YouTube
Relatable Content       | Centering on Health Motivation and Mental Health
Community Engagement    | Through Support Groups and Contests
Influence Partnerships  | Through influencers who shared similar experiences or with smaller but highly engaged followings
Messaging and Tone      | Empowering Language to be used, focusing on growth, self-improveent and well-being over appearance
Product Alignment       | Tailored Fitness Programs designed for overwreight individuals

Future work could also focus on refining the clustering model, perhaps by experimenting with different clustering algorithms or incorporating additional demographic or behavioral features to enhance the understanding of group dynamics. We can also re-analyze new membership numbers after a few months to review the effectiveness of the social marketing proposal.

## AI Ethics
This project works with sensitive personal data, such as demographic information, income, and psychological states, and could potentially raise significant privacy concerns. Let us consider the following areas.

### Privacy and Confidentiality
To ensure PDPA is adhered to, it is crucial to ensure that all data is anonymized so no personal identifiable information is exposed. Access to original data should be secured and limited to avoid privacy breaches, putting individuals at risk of misuse of their data.

### Fairness and Bias
Clustering is based on eight demographic features in this project. If the model is trained on biased data, it may reinforce stereotypes or lead to discriminatory preferences. i.e. A high concentration of 20-25 age group was observed at the start of the data pre-processing, and straight Caucasian male was also identified through the cluster identification. The data is heavily represented by young straight Caucasian males which could result in a skewed conclusion being tied to this group of individuals. We have to continuously monitor and evaluate the model's performance across different demographic groups so as to maintain fair treatment to all groups.

### Accuracy of Interpretation
Clusters might be wrongly used to make assumptions about individuals or groups. In this project, we could end up doing a social marketing program for a wrongly identified target group. This could result in wastage of resources in developing and implementing the program. Therefore the limitations of the model and its findings have to be clearly communicated. Whenever use, context and caution in interpreting the results have to be provided, emphasizing that clustering does not imply justification for discriminatory actions.

### Accountability and Transparency
Data science projects should be transparent about methodologies, data sources, and decision-making processes. We should main open communication with stakeholders about the projects's methodologies, goals, and findings. Thereafter establish accountability mechanisms to address any ethical concerns or unintended consequences.

### Informed Consent
Data used in this project must have been collected with explicit consent, where participants are fully aware of how their data will be used, stored, and shared. Using data without consent or repurposing for different objectives than originally intended would violate ethical standards and legal requirements.

## Source Codes and Datasets
Data preprocessing and model python files, and dataset can be found in GitHub repo link here.
https://github.com/meecatmeow/ITD214_project

Thank you for your attention.
