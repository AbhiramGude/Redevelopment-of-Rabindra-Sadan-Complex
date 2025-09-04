# Rabindra Sadan Cultural Complex - Public Sentiment Analysis

This repository analyzes Google Maps reviews of the **Rabindra Sadan Complex** in Kolkata, India.  
The objective is to understand how people experience the complex from an architectural perspective and derive insights to guide a **redevelopment proposal** that preserves valued cultural identity while creating a renewed image for Kolkata.

---

## Project Overview

This project applies **natural language processing (NLP)** techniques to public reviews, extracting sentiment and identifying key aspects of user experience.  
The results are clustered into architectural categories to highlight strengths to preserve and weaknesses to address during redevelopment.

---

## Data

- **Source**: Google Maps Reviews  
- **Total Reviews**: 9,464 (initial dataset)  
- **Relevant Columns**:  
  - `title`  
  - `stars`  
  - `review`  

### Preprocessing Steps

- Removed reviews with missing text.  
- Dropped irrelevant metadata (`url`, `reviewUrl`, `name`).  
- Translated Bengali reviews into English for consistency.  
- Created a normalized DataFrame (`sentiment_df`) with fields:  
  - `location`  
  - `stars`  
  - `review`  
- Cleaned review text for TF-IDF analysis:  
  - Converted to lowercase  
  - Removed punctuation and special characters  
  - Removed stop words  

---

## Analysis Steps

1. **Star Rating Distribution**  
   - Calculated averages and distributions of star ratings per space.  

2. **Sentiment Analysis**  
   - Applied **VADER** for polarity scores (positive, neutral, negative, compound).  
   - Applied **BERT** for contextual classification (positive, negative).  
   - Compared sentiment distributions between VADER and BERT.  

3. **Correlation Between Stars and Sentiment**  
   - Generated scatter plots and box plots of BERT sentiment scores vs star ratings.  
   - Created heatmaps showing sentiment across ratings.  
   - Identified conflicting cases (e.g., positive review text with low star rating).  

4. **Aspect Extraction (TF-IDF Bigrams)**  
   - Extracted top two-word phrases from reviews.  
   - Examples: *cinema hall*, *ticket price*, *film festival*, *sound system*, *art gallery*.  

5. **Aspect Clustering**  
   - Defined **7 architectural clusters** to group review content:  
     1. Ambience & Spatial Quality  
     2. Cultural Programming & Events  
     3. Access & Connectivity  
     4. Auditorium & Technical Infrastructure  
     5. Amenities & Services  
     6. Heritage & Identity  
     7. Community & Social Role  

---

## Next Steps

- Normalize sentiment counts per aspect and per location.  
- Visualize proportion of positive/negative sentiment for each aspect.  
- Use insights to propose targeted design strategies for the **redevelopment of the Rabindra Sadan Complex**.  
