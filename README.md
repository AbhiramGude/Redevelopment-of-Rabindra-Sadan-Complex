# Rabindra Sadan Cultural Complex - Public Sentiment Analysis

This repository analyzes Google Maps reviews of the **Rabindra Sadan Cultural Complex** in Kolkata, India.  
The objective is to understand how people experience the complex from an **architectural perspective** and derive insights to guide a **redevelopment proposal** that preserves valued cultural identity while creating a renewed image for Kolkata.

---

## Project Overview

This project applies **natural language processing (NLP)** and **sentiment analysis** to public reviews.  
The results are clustered into architectural categories to highlight **strengths to preserve** and **weaknesses to address** in redevelopment planning.

---

## Data

- **Source**: Google Maps Reviews  
- **Total Reviews**: ~9,464 (initial dataset)  
- **Relevant Columns**:  
  - `title` (location within the complex)  
  - `stars` (1–5 user rating)  
  - `review` (text of review)  

### Preprocessing Steps

- Removed reviews with missing text.  
- Dropped irrelevant metadata (`url`, `reviewUrl`, `name`).  
- Translated Bengali reviews into English for consistency.  
- Created normalized DataFrame (`sentiment_df`) with fields:  
  - `location`  
  - `stars`  
  - `review`  
- Cleaned review text for aspect extraction:  
  - Converted to lowercase  
  - Removed punctuation and special characters  
  - Removed English stop words  

---

## Analysis Workflow

### 1. Star Rating Distribution
- Calculated averages and distributions of ratings per space.  
- Identified spaces with consistently high/low ratings.  

### 2. Sentiment Analysis
- Applied **VADER** to compute polarity scores (positive, neutral, negative, compound).  
- Applied **BERT** to classify reviews as **POSITIVE / NEGATIVE** with confidence scores.  
- Compared outputs of VADER vs BERT.  

### 3. Correlation Between Stars and Sentiment
- Scatter plots and box plots of BERT sentiment scores vs star ratings.  
- Heatmaps showing sentiment distribution across ratings.  
- Flagged reviews with mismatched sentiment and stars (e.g., positive text but 2 stars).  

### 4. Aspect Extraction (TF-IDF Bigrams)
- Extracted frequent two-word phrases from cleaned reviews.  
- Examples:  
  - *cinema hall*  
  - *ticket price*  
  - *film festival*  
  - *sound system*  
  - *art gallery*  

### 5. Aspect Clustering
To make findings architecturally relevant, bigrams and features were grouped into **7 clusters**:

1. **Ambience & Spatial Quality**  
   (e.g., *nice place, wonderful ambience, crowded place*)  

2. **Cultural Programming & Events**  
   (e.g., *film festival, cultural programs, art exhibition*)  

3. **Access & Connectivity**  
   (e.g., *metro station, parking facility, traffic issues*)  

4. **Auditorium & Technical Infrastructure**  
   (e.g., *sound system, seating, acoustics, lighting*)  

5. **Amenities & Services**  
   (e.g., *ticket price, food court, restrooms, staff service*)  

6. **Heritage & Identity**  
   (e.g., *Rabindra Sadan, cultural hub, art lovers, heritage value*)  

7. **Community & Social Role**  
   (e.g., *hangout with friends, family time, meeting place*)  

### 6. Aspect-Based Sentiment Aggregation
- Positive and negative sentiment counts aggregated for each aspect per location.  
- Normalization applied:  
  - By total reviews mentioning that aspect (aspect-level proportion).  
  - By total reviews in the location (location-level proportion).  

### 7. Visualization
- Bar plots and spider plots showing sentiment per aspect and location.  
- Heatmaps highlighting critical pain points.  

---

## Key Findings

- **Overall Positive Perception**  
  - Spaces like **Nandan** and **Rabindra Sadan** enjoy very high average ratings and positive sentiment.  
  - Strong cultural attachment is evident.  

- **Strengths in Culture and Heritage**  
  - Aspects related to *cultural events, heritage, and community role* dominate positive sentiment.  
  - Visitors value the **identity of Kolkata’s cultural hub**.  

- **Areas for Improvement**  
  - **Auditorium & Technical Infrastructure**:  
    Frequent complaints about sound, seating comfort, and acoustics.  
  - **Ambience & Spatial Quality**:  
    Overcrowding and spatial discomfort mentioned in large venues.  
  - **Access & Connectivity**:  
    Parking and traffic consistently noted as pain points.  
  - **Amenities & Services**:  
    Food, restrooms, and staff management need upgrades.  

- **Small Venues with Risk**  
  - Places like **Raju’s Kitchen, Sainik Bhawan, Kolkata Information Centre** have relatively higher negative sentiment, suggesting deeper systemic issues.  

---

## Design Inferences for Redevelopment

1. **Preserve and Enhance Core Strengths**  
   - Protect the cultural functions and heritage identity.  
   - Build on the strong community and social role of the complex.  

2. **Targeted Functional Upgrades**  
   - Modernize auditorium infrastructure: seating, lighting, acoustics.  
   - Redesign high-traffic areas to reduce congestion.  

3. **Improve Access & Amenities**  
   - Redesign parking, improve transit integration.  
   - Upgrade food courts, restrooms, and ticketing facilities.  

4. **Strategic Modern Integration**  
   - Introduce **contemporary design language** where necessary (e.g., underperforming areas).  
   - Balance heritage preservation with modern public space design.  

5. **Prioritize User Comfort & Experience**  
   - Make visitor journey seamless, accessible, and comfortable.  
   - Focus on ambience and spatial quality as drivers of satisfaction.  

---


## Author

This repository was created as part of an **architectural thesis on cultural precinct redevelopment**, exploring the intersection of **data-driven analysis** and **design thinking** by **Gude Abhiram (21AR10014)**, **ARP, IIT Kharagpur**
