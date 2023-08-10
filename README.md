# Political-Influence-Youtube-Scraper
![word cloud](https://github.com/chasediaz6/Political-Influence-Youtube-Scraper/assets/52427910/e2edd216-5c66-411e-8705-46f8d4846fd1)

The goal of this project is to model the influences shaping a given local-level politicians’ legislative agenda from their media appearances. To accomplish this, Python code was developed to scrape YouTube search results for a given politician and extract meaningful information from each media appearance. **This includes highlighting the outlets they are most frequently appearing on, the topics and legislation they are frequently discussing, and describing the extent of their reach**. This scraper enables users to automate the data collection to quickly gain these insights for any politician, which would otherwise be extremely time- consuming to complete manually.

## Project Overview
By retrieving YouTube search results for a specific politician and utilizing Natural Language Processing (NLP) techniques, we can extract meaningful information from the captions of each video. The manual process of collecting and analyzing this data for even a single politican would be extremely time-consuming. However, by automating the data retrieval and analysis tasks, we significantly reduce the time and effort required to generate these insights. By analyzing the text captions and search results data, we can identify patterns and generate summary statistics on the following aspects:

1. Media Appearances: Determine the outlets where the politician appears most frequently. The scraper retrieves the top search results for each politician and scrapes available data for each video, including the video title, description, statistics, and the channel it was posted from. This information helps understand which media platforms are influencing the politician's public presence.
![channel stats](https://github.com/chasediaz6/Political-Influence-Youtube-Scraper/assets/52427910/5c78b354-0427-4ae7-9eb5-d07f5838404f)

2. Identify Influences: Identify the topics and legislation that a politician frequently discusses in their media appearances. This analysis provides insights into their legislative agenda and policy priorities. By parsing the captions from each video (where available), the code identifies the most common entities discussed using Named Entity Recognition (NER) using the spacy library. These frequently discussed topics represent potential influences. Users can provide a list of keywords as parameters to the **fill** function to identify which videos contain the given keywords. This functionality allows for quick identification of videos that mention specific topics or legislation of interest.
![keywords_found](https://github.com/chasediaz6/Political-Influence-Youtube-Scraper/assets/52427910/8ada9a1b-b5f5-4268-987b-0783b7148eae)

3. Reach Analysis: Assess the extent of the politician's reach by examining the number of views, engagement metrics, or other relevant indicators. This information helps gauge the visibility and impact of their media appearances, and can be used for comparison to other politicians.


### Insights and Analysis
The project also provides code to generate insights from the YouTube data collected by the scraper:

* Video + Channel Statistics: The project generates a dataframe detailing the data for each video from the scraped YouTube search results. This allows users to identify the channels where a politician appears most frequently, along with the number of views and subscribers for each channel. Additionally, two plots are generated: one visualizing the total views for each channel and another visualizing the number of views for the top 10 most viewed videos from the search results.
* ![video stats](https://github.com/chasediaz6/Political-Influence-Youtube-Scraper/assets/52427910/f0309363-520a-4b4a-ba64-5c04b2b95484)

* Topic Modeling: Using the Top2Vec Python library, the project implements a topic model on the scraped data. The topic model clusters the words and phrases used in the video captions to identify specific topics. The resulting list of topics includes associated keywords that frequently appear within each topic.
![topic model keywords](https://github.com/chasediaz6/Political-Influence-Youtube-Scraper/assets/52427910/fd084bf3-369a-4ab9-9bae-72467b0987e8)

* Topic Model Word Cloud: A visual representation of the popular words for each topic recognized by the topic model. The size of each word in the word cloud corresponds to its frequency and relevance in specifying the topic.
![word cloud](https://github.com/chasediaz6/Political-Influence-Youtube-Scraper/assets/52427910/e2edd216-5c66-411e-8705-46f8d4846fd1)

### Data Output
* Search Results: This dataset contains the top 25 YouTube search results for each politician, including video titles, descriptions, channel names, video and channel statistics (views, subscribers), and video links. This dataset enables further investigation into each politician's media appearances.

* Keywords Found: This dataset demonstrates the usage of keywords (such as "climate," "emissions," and "renewable energy") to identify specific topics in each YouTube video. It shows which videos contain the given keywords, allowing users to pinpoint relevant videos quickly.

* Entities: This dataset presents the most commonly recognized entities extracted using the NER model from the search results of the 10 politicians. Entities such as names, organizations, or legislation related to each politician's media appearances are listed. These entities can indicate influences, and further investigation is recommended for previously unknown influences.

### Key Libraries and Techniques Used
The project relies on the following libraries and techniques:

* [YouTube Data API](https://developers.google.com/youtube/v3): Utilizes the YouTube Data API to search for videos and retrieve relevant metadata, including captions. A API key will be needed to access the API. 

* Natural Language Processing (NLP): NLP libraries [spacy](https://spacy.io/api/doc) and [top2vec](https://top2vec.readthedocs.io/en/latest/) are used to process the text data extracted from the video captions. These libraries enable various NLP tasks such as text preprocessing, topic modeling, sentiment analysis, and more.

## How to Use the Project
To use this YouTube search results scraper for politicians' media appearances, follow these steps:

1. Obtain API Credentials: Obtain the necessary API credentials from the YouTube Data API by creating a project and enabling the YouTube Data API v3.

2. Set Up the Environment: Set up a Python environment with the required dependencies, including spacy and top2vec.

3. Configure the Project: Configure the project by specifying the politician's name, search parameters, and any other relevant settings.

4. Run the Scraper: Execute the YouTube search results scraper script, which will make API requests, retrieve search results, and extract captions from the videos.

5. Perform NLP Analysis: Process the text data using NLP techniques such as text preprocessing, topic modeling, or sentiment analysis. Generate summary statistics based on the insights derived from the analysis.

6. Interpret the Results: Interpret the summary statistics to gain a comprehensive understanding of the politician's media appearances, influences, and reach.

## Conclusion
The results generated from the topic models yielded consistent results comapred to the manual analysis conducted for each of the 3 local-level politicians. With this, the scraper and code in yt_scraper.ipynb can accurately describe the influences shaping a politicians legislative agenda. This automated analysis can save plenty of time and effort versus conducting it manually, and does so objectively. 

By utilizing the YouTube search results scraper and NLP techniques, this project aims to provide valuable insights into the influences on local-level politicians from their media appearances. The analysis of captions and subsequent generation of summary statistics can help researchers, policymakers, and the general public quikckly understand the media landscape surrounding specific politicians and the topics they frequently discuss.

