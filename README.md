Project Overview
This project aims to analyze public perception of the Rabindra Sadan Complex in Kolkata, India, using Google Maps reviews. The goal is to understand how people experience the space from an architectural perspective and derive insights to inform a potential redevelopment proposal for the complex, focusing on retaining valued elements while creating a new identity for Kolkata.

Data
The data used in this analysis consists of Google Maps reviews collected for various spaces within the Rabindra Sadan Complex. The data was initially in .xlsx format and combined into a single pandas DataFrame.

Data Source: Google Maps Reviews
Total Reviews: 9464 (initially)
Relevant Columns: title, stars, name, reviewUrl, text
Data Preprocessing
The raw data underwent several preprocessing steps to prepare it for sentiment analysis and aspect extraction:

Handling Missing Values: Reviews with missing text were removed.
Dropping Irrelevant Columns: Columns like url, reviewUrl, and name were dropped.
Translation: Bengali reviews were translated to English to ensure consistent language for analysis.
Creating sentiment_df: A new DataFrame was created with relevant columns renamed to space, stars, and review. Empty reviews after translation were removed.
Text Cleaning for Aspect Extraction: Review text was cleaned by converting to lowercase, removing punctuation and special characters, and removing standard English stop words to prepare for TF-IDF analysis for aspect extraction.
Analysis Performed
The following analyses were conducted on the preprocessed data:

Star Rating Distribution: Visualized the distribution of star ratings for each space and calculated the average rating.
Sentiment Analysis (VADER): Applied VADER sentiment analysis to the reviews to get polarity scores (negative, neutral, positive, compound) and classified sentiment based on the compound score.
Sentiment Analysis (BERT): Applied a pre-trained BERT sentiment analysis model to classify reviews as POSITIVE or NEGATIVE and obtain sentiment scores.
Comparison of Sentiment Models: Compared the overall sentiment distribution predicted by VADER and BERT.
Correlation Analysis: Visualized the relationship between star ratings and BERT sentiment scores using scatter plots and box plots, and created a heatmap showing the distribution of BERT sentiment across star ratings.
Identification of Conflicting Reviews: Displayed examples of reviews with conflicting star ratings and BERT sentiment (e.g., 1-star positive sentiment, 5-star negative sentiment).
Aspect Extraction (TF-IDF Bigrams): Used TF-IDF on cleaned review text to identify the most important bigrams (two-word phrases) as potential indicators of architectural aspects.
Aggregated Sentiment per Refined Aspect per Location: Defined specific architectural aspects and mapped review terms/phrases to these aspects. Aggregated the positive and negative sentiment counts for each aspect within each location.
Visualization of Aspect Sentiment: Visualized the aggregated sentiment counts and normalized sentiment proportions per architectural aspect for each space using bar plots and spider plots.
Key Findings and Inferences
The analysis revealed several key insights into public perception of the Rabindra Sadan Complex spaces:

Overall Positive Perception: The complex is generally well-regarded, with high average star ratings and a large proportion of positive reviews, especially for the major cultural venues like Nandan and Rabindra Sadan.
Strengths in Culture and Community: Aspects like "Cultural Programming & Events," "Heritage & Identity," and "Community & Social Role" consistently receive high positive sentiment, highlighting the success of the complex as a cultural and social gathering space.
Areas for Improvement: Despite overall positivity, specific areas receive notable negative feedback:
Auditorium & Technical Infrastructure: This aspect shows significant negative mentions in Nandan and Rabindra Sadan, suggesting a need to modernize technical facilities, seating, acoustics, etc.
Ambience & Spatial Quality: While generally positive, negative feedback here, particularly in high-volume spaces, points to potential issues with crowdedness and spatial comfort.
Access & Connectivity and Amenities & Services also have some negative mentions, indicating potential pain points related to traffic, parking, and facilities.
Spaces Requiring Deeper Investigation: Spaces with lower review volumes and higher proportions of negative sentiment (Raju's Kitchen, Kolkata Information Centre, Sainik Bhawan) suggest more significant underlying issues that warrant further investigation beyond review data.
Design Strategies and Inferences for Redevelopment
Based on the public feedback, the redevelopment plan can strategically focus on:

Preserving and Enhancing Core Strengths: Maintain and improve the cultural functions, community gathering spaces, and positive spatial qualities that are highly valued by the public.
Targeted Functional Upgrades: Prioritize modernizing technical infrastructure in performance venues and improving access, connectivity, and amenities to address specific pain points identified in the reviews.
Addressing Spatial Challenges: Implement design solutions to manage crowdedness and enhance spatial comfort in high-traffic areas.
Strategic Modern Integration: Introduce contemporary architectural elements thoughtfully, particularly in areas requiring significant intervention (like Raju's Kitchen or Sainik Bhawan) or in new public spaces, to create a new identity while respecting the complex's heritage.
Focus on User Experience: Ensure the redevelopment prioritizes a positive visitor experience by addressing functional issues and enhancing comfort and accessibility.
By leveraging the insights from this sentiment analysis, the redevelopment of the Rabindra Sadan Complex can build upon its existing strengths while creating a more functional, comfortable, and vibrant space that resonates with the public and establishes a renewed identity for Kolkata.
