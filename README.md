# NLP for San Francisco Airbnb User Comments Analysis


*Team Member: Hua Yang, Md Omar Obaid, Arielle Williams, Lan Huang*<br>


*Introduction*<br>

*Airbnb has created a new revolution in the travel industry, shifting the traditional trend of people using hotels as their preferred destinations. This change in travel behavior has not only affected tourists but also opened new investment opportunities for many real estate investors. Currently, Airbnb boasts an impressive network of four million hosts worldwide.[2]*<br>

*Problem Statement and Research Question(s)*<br>
*Identifying the problem: Given its enormous influence and potential for investment, we aim to utilize Natural Language Processing (NLP) to extract valuable business insights. Our primary focus is to provide Airbnb hosts with ideas on how to enhance customer satisfaction and achieve success in running their Airbnb rental business. So, the problem is to utilize Natural Language Processing (NLP) to extract valuable business insights from customer reviews of Airbnb listings in San Francisco.*<br>

*Background research (prior studies): In preparation to effectively utilize our NLP technology and achieve our goals, we extensively reviewed relevant research articles. We explored various topics, including techniques for identifying valuable insights around specific subjects (Hhye Won Shin, 2020)[2], the combination of LDA (Latent Dirichlet Allocation) with deep neural language models to enhance result effectiveness (Yibo Wang, 2017)[10], and methods for leveraging pre-trained libraries to label sentiments. (Jiaxuan Wang, 2023)[6].*<br>

*Additionally, we delved into the use of NLP to determine optimal rental prices (Md Didarul Islam, 2022)[7], and explored approaches for extracting customer sentiments by comparing hotel and Airbnb reviews in New York (Baojun Gao, 2022)[3]. These comprehensive research materials has equipped us with valuable insights and methodologies to conduct our analysis effectively.*<br>

*Importance of investigation: It is important to investigate this problem because understanding customer sentiments expressed in reviews can provide valuable insights to Airbnb hosts, enabling them to improve their offerings, manage their reputation, and stay competitive.*<br>

*Additionally, it empowers potential guests to make well-informed decisions and set realistic expectations for their Airbnb experience.*<br>

*Data Source: To gather the necessary data, we have sourced our dataset from insideAirbnb.com. (Inside Airbnb - Adding Data to the Debate, 2023)[5]. Our observation sample concentrates on the city of San Francisco for three main reasons. Firstly, San Francisco ranks third among the cities with the highest median house prices, making it a lucrative market for short-term rentals. (10 Most Expensive Cities In The US, 2023)[1]. Secondly, it is among the top ten most visited cities in the US, indicating a high demand for accommodations (Start Your 2023 Domestic Travel From These Most Visited Cities In The US, 2023)[8]. Lastly, San Francisco is ranked fifth among the happiest cities (The Happiest Cities in America Are in California, According to a New Study—See Where Your Ranks on the List, 2023)[9].*<br>

*Based on these remarkable attributes and the multitude of compliments this city receives, we have selected San Francisco as our focal point for analysis.*<br>

*For the sake of timeliness, we have selected customer reviews from the year 2022. These reviews encompass 4,286 listings, totaling 70,720 individual reviews.*<br>

*The dataset comprised 6 columns: 'listing_id', 'id', 'date', 'reviewer_id', 'reviewer_name', and 'comments'. Upon initial data exploration, we observed that the majority of reviews were concentrated between May and October, with relatively fewer reviews during the period from November to February.*<br>

*Project Goal and the identified issue: The goal of the project is to analyze user reviews of Airbnb rentals in San Francisco to extract positive and negative sentiments and identify the relevant words used in the reviews. The objective is to provide valuable insights to Airbnb hosts to enhance customer experience and achieve success in their rental businesses.*<br>

*One of the issues we identified during the sentiment analysis is that even though some of the comments were negative, our model was registering those comments as positive.*<br>

*Rationale for importance: Text analytics using NLP can uncover hidden patterns, sentiments, and insights from large volumes of textual data, which can be crucial for businesses like Airbnb. Understanding customer sentiments and preferences can drive improvements in services and offerings, leading to increased customer satisfaction and business success.*<br>

*Some of the research questions we tried to figure out during the course of our project are as follows:*<br>

*▪	What are the most common positive sentiments expressed by customers in their reviews of San Francisco Airbnb rentals?*<br>
*▪	What are the most common negative sentiments expressed by customers in their reviews of San Francisco Airbnb rentals?*<br>
*▪	Which aspects of Airbnb rentals in San Francisco are most frequently mentioned in positive reviews?*<br>
*▪	Which aspects of Airbnb rentals in San Francisco are most frequently mentioned in negative reviews?*<br>
*▪	How do customer sentiments vary throughout the year in San Francisco Airbnb reviews?*<br>
*▪	How can Airbnb hosts use sentiment analysis to improve customer satisfaction and business performance in San Francisco?*<br>

*Methodology and dataset*<br>

*Our dataset comes from insideairbnb.com and contains reviews on listings from San Francisco Airbnb properties. The dataset obtained from Inside Airbnb site is sourced from publicly available information from the Airbnb website. Our datasource is reliable since it contains reviews from actual airbnb users. The original dataset contains over 300,000 records ranging from the year 2009 to 2023. For the purposes of our study, we will be focusing on reviews from the most recent complete year, 2022.  Once we reduced the dataset to the year 2022, our dataset contains 70,720 reviews and 4,286 unique listing ids.. The dataset used consists of six columns including listing_id, ID, Date, reviewer_ID, reviewer_name, and comments.*<br>

*The first step in our process involved cleaning the dataset.  This process includes removing null values, unnecessary punctuation, whitespace and stopwords from the dataset. Additional preprocessing included lemmatization, which is a process of reducing a word to its base form.   Once cleaned, the steps we took to analyze the reviews include:*<br>

*Creating a wordcloud: The purpose of creating a wordcloud is to create visualization of text data and get insights into the trends and patterns within the dataset. *<br>

*Determine relevancy of words: TF-IDF is a method used in natural language processing and information retrieval. We used Term-Frequency- Inverse Document Frequency-(TF-IDF,), to measure the importance of terms within the reviews. *<br>

*Performing Sentiment Analysis:  Sentiment analysis is the process of detecting positive and negative sentiment in textual data. To analyze sentiment, we employed a labeled dataset and leveraged pre-trained libraries. DistilBERT served as our model for training and evaluating its accuracy. We also utilized textblob, a Python library used for processing textual data. *<br>

*Text Clustering(Unsupervised learning): Text clustering  is an unsupervised algorithm that groups similar data together  This method is useful for understanding what your dataset is  mainly about and what different categories your data belongs to.*<br>

*By integrating these NLP technologies into our methodology, we aim to derive meaningful and actionable insights for the benefit of our Airbnb hosts.*<br>

*For supervised learning (Sentiment Analysis), we used the pre-trained library TextBlob on the labeled dataset and then trained and evaluated DistilBERT on a reduced dataset (1/10) with 7,071 reviews, using 70% for training and 30% for validation. We used logits as the output, an Adam optimizer with a learning rate of 3e-4, and BinaryCrossentropy as the loss function.*<br>

*For unsupervised learning (Topic Clustering), we employed BERTopic modeling to extract topics and interpreted them, utilizing Get_topic_info to determine the total number of topics. We also used visualization techniques to present the clustering results effectively.*<br>

*Analysis and Results*<br>

*The analysis and findings reveal that January and February received the lowest number of reviews, while August and September received the highest number of reviews in the city of San Francisco.*<br>

*It seems that a significant number of customers in San Francisco had a wonderful experience and expressed positive experiences in the city San Francisco. The Emotion analysis further supports this, as evident from the high counts of positive emotions such as joy, trust, while negative emotions like sadness, disgust were relatively less common. *<br>

*positive: 38591, joy: 26469, trust: 26738, anticipation: 14795, sadness: 4406, surprise: 8257,*<br>
*negative: 2200, disgust: 513, fear: 774, anger: 615*<br>

*The Emotion analysis result aligns with the Sentiment analysis, further confirming this pattern, showing that 94% of the overall comments carried positive sentiments for the city of San Francisco.*<br>

*The word cloud for negative reviews with a compound score less than -0.5 indicated that common concerns were also related to the cleanliness and conditions of the city, rather than solely focusing on the accommodation itself. (Comments such as “San Francisco is a terrible dirty city don’t waste your money. This Airbnb was mediocre. Wasn’t impressed”)*<br>

*The word cloud for positive reviews with a positive score greater than 0.5 highlighted words like "clean," "great," and "beautiful," suggesting customers' appreciation for the pleasant aspects of their stay.*<br>

*BERTopic analysis provided more context by identifying the most popular topics in the comments. Notably, these topics centered on the convenience of accessing various amenities, with a focus on parking availability, a major concern in San Francisco. Customers also expressed their opinions about the comfort of beds and bedrooms, as well as the cleanliness of the rooms. It appears that these factors have a significant influence on the overall experience of visitors to San Francisco.*<br>

*Discussion*<br>

*The project's findings reveal that San Francisco generally receives positive reviews, and most customers expressed positive sentiments, demonstrating satisfaction with their accommodations and appreciation for the hosts' hospitality. This information is valuable to gain insights into the overall perception and identify strengths and weaknesses. Moreover, the identification of popular topics in the comments, such as amenities' proximity and accommodation comfort, can assist hosts in catering to customer preferences and enhancing their offerings. The word cloud analyzes further understanding common themes and concerns, pinpointing specific areas that require attention and potential opportunities for improvement.*<br>

*The main limitation of this is connected to the lack of a labeled dataset. A labeled dataset would permit the use of supervised machine learning techniques, which would provide more accurate results. Moreover, some grammatical rules could not be truly explored, due to slang phrases, idioms, double negative terms, etc. For instance, a comment such as “Exceptional place. I was very sad to leave!” would be classified as negative, although the reviewer shared a positive aspect. However, these cases are limited, and results could not be influenced by certain rarely presented phrases. *<br>

*Further research could explore the relationship between negative context of reviews and certain characteristics of the properties. It could also compare different times as pandemic has seriously affected the housing industry worldwide. it would be interesting to compare the results of this analysis to post Covid datasets.*<br>

*Conclusion*<br>

*The analysis of Airbnb comments in San Francisco during 2021 revealed valuable insights into the overall customer experiences. Most customers expressed positive sentiments, demonstrating satisfaction with their accommodations and appreciation for the hosts' hospitality. However, the project also identified areas for improvement, as some negative comments highlighted specific concerns that need attention. Hosts can utilize this constructive feedback to make targeted enhancements, enhancing the guest experience and fostering a positive reputation.*<br>
 
*References*<br>

*[1]	10 Most Expensive Cities In The US. (2023, February 24). Retrieved from rocketmortgage: https://www.rocketmortgage.com/learn/most-expensive-cities-in-the-us*<br>
*[2]	AIRBNB STATISTICS [2023]: USER & MARKET GROWTH DATA. (2023). Retrieved from searchlogistics: https://www.searchlogistics.com/learn/statistics/airbnb-statistics/#:~:text=There%20are%20currently%20over%204,have%20Airbnb%20listings%20in%20them*<br>
*[3]	Baojun Gao, M. Z. (2022). Journal of Hospitality and Tourism Management. Different voices between Airbnb and hotel customers: An integrated analysis of online reviews using structural topic model, 131. doi:https://doi.org/10.1016/j.jhtm.2022.03.004*<br>
*[4]	Hhye Won Shin, A. F. (2020). International Journal of Tourism Research. Peer-to-peer accommodation: A meta-analysis of factors affecting customer satisfaction and loyalty, 596. Retrieved from https://doi.org/10.1002/jtr.2428*<br>
*[5]	Inside Airbnb - Adding Data to the Debate. (2023, June 05). Retrieved from Inside Airbnb : Get the Data: http://data.insideairbnb.com/united-states/ca/san-francisco/2023-06-05/data/reviews.csv.gz*<br>
*[6]	Jiaxuan Wang, Y. S. (2023). Cities. Insights in a city through the eyes of Airbnb reviews: Sensing urban characteristics from homestay guest experiences, 140. doi:https://doi.org/10.1016/j.cities.2023.104399*<br>
*[7]	Md Didarul Islam, B. L. (2022). Machine Learning with Applications. 09. doi:https://doi.org/10.1016/j.mlwa.2021.100208*<br>
*[8]	Start Your 2023 Domestic Travel From These Most Visited Cities In The US. (2023). Retrieved from thetravel: https://www.thetravel.com/most-visited-cities-in-the-us/#new-orleans-louisiana*<br>
*[9]	The Happiest Cities in America Are in California, According to a New Study—See Where Your Ranks on the List. (2023). Retrieved from marthastewart: https://www.marthastewart.com/8376605/happiest-cities-in-america-2023#:~:text=After%20researching%20180%20of%20the,second%20year%20in%20a%20row*<br>
*[10]	Yibo Wang, W. X. (2017). Decision Support Systems. Leveraging deep learning with LDA-based text analytics to detect automobile insurance fraud, 95. doi:https://doi.org/10.1016/j.dss.2017.11.001.*<br>


