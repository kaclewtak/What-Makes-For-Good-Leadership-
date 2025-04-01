# Project Overview

In depth analysis of Glassdoor reviews, gaining insights on what might make for good (or bad) leadership. This project looks to search through employee reviews and determine whether or not we might be able to extract some knowledge about whether or not we can determine what makes for a good workplace leader. This is to be accomplished by extracting sentiments and topics, and performing clustering on the data across a variety of categories.

The dataset used for this project is a collection of over 8 million employee reviews which has been scraped from the website Glassdoor, made available on Kaggle. This is a diverse dataset and contains ordinal, categorical, textual, and numerical datatypes.

Ultimately, this project serves to attempt to answer the following questions:

    What makes a workplace good or bad?
    Are there indicators for what a good manager/ceo might be?


# Description of Methods

Text preprocessing and exploratory data analysis are all completed in a manual fashion for explainability, with tokenization, lemmatization, and stop word removal being handled by the SpaCy package. Preprocessing is handled in two stages. The first stage primarily focuses on cleaning the dataset as a whole. I handle the removal of unnecessary columns, handling of problematic NaN values, and the cleaning of text columns which may contain information which is desired, but mixed with text that holds no value. I note here that I leave many instances of NaN values in the dataframe as their removal would result in too much dataset loss. Instead I utilize filtering to selectively find the necessary data in order to populate data subsets.

The EDA performed is done so using both WordClouds and the plotting of distributions. Wordclouds are well suited to this topic as we are handling a question which has a largely subjective aspect to it. The "goodness" of leadership can be categorized in many different ways, and can be industry dependent. In order to realistically keep this project within scope, I will only be performing analyses at a higher level. However, I must acknowledge that there is significant depth to this dataset, for which a wide variety of methods could be used.

For this project I primarily leverage LDA topic modeling to come to my conclusions. Sentiment analysis was briefly considered, however given that my dataset already contains categories in which reviewers could leave positive/negative remarks or ratings, I found this to be redundant. Instead I opt for the modeling of topics and using the existing categories as filters in order to more finely inspect which aspects of leadership individuals liked or disliked the most.

# Conclusions

Ultimately, there are clear topics and term associations that can be seen between the various data subsets. Viewing the data at the extremes of the ratings, either 5 or 1, paints a distinctly clear picture of what makes for a healthy workplace and what indicates poor management/leadership.

To answer the question of "Are there indicators for what a good manager/ceo might be?" we must consider the following findings.

Indicators of positive management and good leaderships, based on the LDA topic results, term saliency, and term relevance are as follows:

    The creation of a positive work environments
    Providing opportunities for employees to learn and grow, either through internal resources or through training
    Employees feel as though the CEO, as well as the company, cares for their wellbeing.
    The presence of strong teamwork and overall positive interpersonal interactions with both leadership and fellow employees.

All of the above characteristics can be brought about by leadership which has a clear understanding of their employees and their needs. Providing value and resources back towards the employees seems to be the greatest indicator of positive leadership sentiment. Positive guidance and team creation comes in as a close supporting factor.

Indicators of negative management and bad leadership, based on the LDA topic results, term saliency, and term relevance are as follows:

    Lack of overall team management, poor organization, and a lack of vision
    Poor or completely lacking employee communication
        Or, when there is communication, reviewers often mentioned that leadership was 'rude' or 'awful'
    Overly high work expectations coupled with long work hours
    A poor work environment
    An underdeveloped or negative work culture which contributes to negative leadership sentiment

The above topics and sentiments are heavily related to how individuals percieve themselves to be treated by those in charge. The inability of leadership to effectively communicate with employees, or even between themselves, appears to curate a poor working environment which is often mentioned in these reviews. Likewise, we can see individuals attributing poor working conditions and bad pay to ineffective leadership.

We can additionally address the other question posited, "What makes a workplace good or bad?"

From the modeled topics, I conclude that most often employees wish to be respected and valued, with their time and efforts being rewarded with compensation that is appropriate. Supporting topics are:

    Opportunities to advance one's own career
    Flexible working hours and/or healthy worklife balance
    Leadership which communicates with, and supports, the employees.

The working environment appears to also play a significant role in determining whether or not a particular job/company would be worth working for. Overall, while there are many caveats to what might make a particular job or company "good", the overwhelming sentiment is that "good" jobs are ones where there is consideration put forward as to the well being of the individual.

# Future Work

In the future, I would like to employ a wide range of sentence transformers and aggregate the topic results together, as to have a more comprehensive topic extraction pass. The current implementation relies on a more traditional LDA method which can be considered "basic" in comparison to more modern methods of topic extraciton. Other considerations would be to include more columns of data from the original dataset and creating a more robust positive/negative scoring system for the reviews. 
