# Data Scraping and Annotation  

## Overview  
This project automates the extraction and annotation of research papers from NeurIPS (https://papers.nips.cc). It consists of two main scripts:  

1. **scraper.py** – Scrapes metadata from NeurIPS for the last 5 years and downloads all research papers.  
2. **annotate.py** – Uses the scraped metadata to categorize papers into predefined categories using AI.  

## Output Files  
- **output.csv** – Contains metadata of research papers (Year, Title, Authors, Paper Link, PDF Link).  
- **annotated.csv** – Contains the same metadata with an additional "Category" column assigned by AI.  

## Process  
1. **Web Scraping**  
   - Extracts paper details: **Year, Title, Authors, Paper Link, PDF Link**  
   - Handles pagination and nested links to retrieve complete data  
   - Saves extracted data to `output.csv`  

2. **Annotation**  
   - Reads `output.csv` and extracts **Title** and **Abstract**  
   - Sends data to Google's Gemini API for categorization  
   - Saves annotated data with categories in `annotated.csv`  

## Categories Used for Annotation  
The AI model classifies papers into one of the following predefined categories:  
- **Deep Learning**  
- **Reinforcement Learning**  
- **Optimization**  
- **Graph Neural Networks**  

## Challenges Addressed  
- **Pagination & Nested Links:** Ensured smooth extraction of metadata from multiple years.  
- **API Rate Limits:** Implemented exponential backoff and randomized delays.  
- **Abstract Extraction Issues:** Handled inconsistent HTML structures.  
- **Error Handling:** Added retry mechanisms for API failures.  

## Precautions  
✅ Respect website **robots.txt** and terms of service.  
✅ Avoid sending too many requests in a short time.  
✅ Ensure API usage does not exceed quotas or incur unexpected costs.  

This project automates the labor-intensive process of research paper categorization using **web scraping + AI annotation**, making it scalable and efficient. 🚀  
