# Extractive-Text-Summarization-of-speeches-by-president-s-of-the-United-States

A detailed repository (report and code files) for explaining the process of Text Analytics and text Summarization

## Introduction and Overview

The data in the world is increasing tremendously. Now is the time when we can get an infinite amount of
data for any topic we seek. Automatic text summarization methods are greatly needed to address the
ever-growing amount of text data available online to both better help discover relevant information and to
consume relevant information faster.[1] Extracting summary of a detailed transcript is an abstract process.
Automating such a process can help parse through a lot of data and help businesses better use their time to
make crucial decisions.[2] This text summarization and analysis report pertains to the ‘State of Union
Address’ and ‘Inaugural Address’ speeches of USA’s last six elected presidents.

In this report, we analyze:

* What keywords were used by each of the presidents and their frequency distribution
* How text ranking works and what were the highest ranked text phrases?
* Named-Entity recognition through parts-of-speech tagging
* What were the topics(agendas) involved in the speeches?
* What was the most dominant topic in each speech?
* What is the trend of Sentiment and Subjectivity of each of the presidents over the years?
* How to carry out text summarization and which model to employ?


**Why do we need Text Summarization and what are the techniques involved?**

So what is the driving force behind the development of such intricate tools to extract context and meaning
from a text? To answer this question let's consider a pragmatic and relatable example. As graduate
students, we refer to several research papers and often the research carried out is overwhelming in terms
of content and complexity. Often we wish for a short-hand version of the entire text that delivers accurate
context and also includes vital information. This is exactly what our project aims to deliver. To carry out
Text Summarization, there are mainly 2 techniques to choose from:

a) *Extractive Text Summarization*: Selecting relevant phrases from the input document and stitching them together to form a summary. For example, consider the source text:
          
          Joseph and Mary rode on a donkey to attend the annual event in Jerusalem. In the city, Mary gave birth to a child named Jesus.

The extractive summary would be:

          Joseph and Mary attend event Jerusalem. Mary birth Jesus.

b) *Abstractive Text Summarization*: The abstractive text summarization algorithms create new phrases and sentences that relay the most useful information from the original text, keeping the original intent — just like humans do.

Source text: 

          Joseph and Mary rode on a donkey to attend the annual event in Jerusalem. In the city, Mary gave birth to a child named Jesus.

Abstractive Summary:

          Joseph and Mary came to Jerusalem where Jesus was born.

We have carried out an extractive summarization of each president’s speech using models like mobilebert & gensim summarizer and contrasted the obtained results with an abstractive summarization model of T5.

## Requirements:

- Packages used and required installments
hdbscan==0.8.26, nltk==3.5, pyLDAvis==2.1.2, pytextrank==2.0.3, selenium==3.141.0,
sentence-transformers==0.3.9, textblob==0.15.3, torch==1.7.0, torchvision==0.8.1+cu101,
tqdm==4.41.1, transformers==3.5.1, umap-learn==0.4.6, vaderSentiment==3.3.2,
wordcloud==1.5.0, yellowbrick==0.9.1
- Google colab compatibility
- Selenium for web scraping ( https://www.selenium.dev/documentation/en/ )
- Chrome webdriver installation ( https://stackoverflow.com/questions/51046454/how-can-we-use-selenium-webdriver-in-colab-research-google-com )


## Methodology:
The speech data for President’s Ronald Reagan, George H W Bush, Bill Clinton, George H Bush, Barack Obama and Donald Trump were collected from this open source(https://millercenter.org/the-presidency/presidential-speeches). To avoid bias and focus on agenda’s of each president in their tenure, we have chosen the ‘Inaugural Address’ and ‘State of Union Address’ speeches of all these presidents. The number of speeches chosen for each president might vary due to the number of years in their respective tenures.

The data was collected from each of the websites by using Selenium on Google Colab. Selenium is an umbrella project for a range of tools and libraries that enable and support the automation of web browsers. At the core of Selenium is WebDriver, an interface to write instruction sets that can be run interchangeably in many browsers. Selenium consists of many functional tools that enable a user to navigate and dynamically scrape data from web resources by using arguments like ‘find_element_by_xpath’, ’find_element_by_css_selector’, etc to locate elements. We developed a python script that employs selenium to navigate through each link in a list of speeches for each president and scrape the entire transcript. For clearly analysing a president’s speech and to contrast the obtained results with another president, we have designed a user-input based architecture.


Check out the report for detailed explanation, EDA, and plots related to this project.
