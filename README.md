# ai_project_group_8
A data analysis class project for Columbia University's AI bootcamp.

## "An Outlook on AI Jobs"
<div align='center'>
    <img src='....' height='300' title='AI Jobs'(image courtesy of....)' alt='an image of a ....'/>

*AI Jobs*[^1]

<div align='left'>

## Project Team Members:
* Nathan Anecone
* Kalvin Anglin
* Peta-Gaye McKenzie
* Odele Pax
* Funda Subasi

## Table of Contents

* [Abstract](#Abstract)
* [Data](#Data)
* [Methods](#Methods)
* [Limitations](#Limitations)
* [Conclusions](#Conclusions)
* [References/Footnotes](#References/Footnotes)

## Abstract

### Project Details

* The objective of our EDA was to address concerns about the oversatuaration of applicants for AI jobs given the increased popularity of the field by examining   the job market trends for these positions. Initially, our parameter for exploring AI jobs was broad and included how trends for this position have impacted many different job sectors, resulting in the following key questions:
    *   What industries are benefitting the most from AI?
    *   Where is the largest demand for AI Jobs? / Insight into workplace flexibility.
    *   How has education adapted to technical job needs?
    *   What skillsets are the most desirable for AI Jobs?

* **Thesis/Hypothesis**: As we see continued growth in tech sectors, will we see education adapt to evolving skillset needs, along with organizations within the sector offering broader workplace flexibility.

The following term are used interchangeably throught the project given the overlap in definitions:

AI
: Development of computer systems capable of performing tasks that typically require human intelligence

ML
: Method of analyzing data to help AI computer systems optimize their functionatility as they learn from vast quantities of data-based scenarios.[^1]

---

## Data

### Datasets

We reviewed datasets that provided the most opportunity for a thorough exploration of our key questions:
* Combined data from US Census API for 2012 - 2022: https://www.census.gov/data/developers/guidance.html
*   Maching Learning Job data: json
* LinkedIn Job Postings for 2023: https://www.kaggle.com/datasets/joebeachcapital/linkedin-jobs
* AI Companies and Profit by Sector for 2022: https://www.kaggle.com/datasets/hansrobertson/american-companies-profits-and-benefits-from-ai



| Data Phases | Details|
| :--- | :--- |
| Fetching  | Google searches, Kaggle, LinkedIn, Census API search    |
| Software Version Control | Repository created on GitHub, GitHub Projects used to create and track tasks based on key questions, Git branch used to upload files to from local computer to remote repository, utilized "compare & pull requests" to compare branch changes before merging into the main branch correlation, comparison, summary statistics, sentiment analysis, and time series analysis   |
| Exploration | Imported CSV files, created dataframes, utlized pandas and python functions to search and select data related to AI jobs, identifying job sectors, experience levels, skills, and employment trends for further analysis    |
| Preparation & Cleanup  |  Utilized dictionarys, list, loops, column slicing, string manipulation, to ensure high quality and structured data is visualized and fed into the machine to identify patterns, correlation, and predictive analysis    |

---

## Methods 

*AI Sectors and Profits:*

AI company and profit dataset was read into notebook to analyze AI trends in number of companies and profit by sector. Grouped certain AI sectors in the dataframe by creating a group_sector() function to loop through a keywords list and replace certain sectors with the appropriate keyword. Performed further analysis through aggregate functions to count the number of AI companies and sum of profits for the top twenty AI Sectors. Used visualization to explore results.

*Tech Workplace Flexibility and Job Level:*

LinkedIn dataset comprised of tech job postings was read into notebook to analyze trends in job levels and job types for the tech sector in the US and abroad. Grouped the dataframe by job level and job type to count the occurences and determine correlation between seriority and workplace flexibility. The job type represented a onsite, remote, or hybrid workplace model. Analyzed the concentration of the respective job types through visualizations. Investigated the top five AI skills required for Associate, Mid, and Senior level AI jobs by applying string match to the dataset to get all AI job listings based on a list of keywords for AI skills. Utilized the count_skill() function, passing in the AI job dataframe and the job level as parameters. Visualized the top three skills by job level for further analysis.

*US Census Predictions* 

Imported Prophet and previously compiled data from US Census API for years 2012 - 2022 which was analyzed to determine the relationship between tech-related jobs, education levels, and unemployment rates. 

Certain column fields from the source dataset were included in the import and other columns were sliced into dataframes to calculate necessary fields. The "Year" column was converted into Datetime format for future use with Prophet. All states were represented in each given year of the dataset, which allowed for grouping by "Year", aggregating by "mean()" , and plotting on a 10-year timeline to visualize national trends in education levels and the percentage of population working in the tech-related field.

Passed data slices into Prophet to provide a 5 years prediction for percentage change in Tech Fields, No Education, Profeessional Education, Unemployment, Bachelor's Degree Completion, Associates Degree Completion, High School Degree Completion, and GED Completion.

*AI vs Non-AI Software Developers:* 

Used LinkedIn dataset for further exploration of employment trends. Performed a comparative analysis to determine the relative proportion of AI jobs to non-AI jobs by applying string match to the dataset to get all job listings based on a list of keywords for AI skills. AI listing and non-AI listings were assigned to separate dataframe for porportion calculation and visualization. 

Investigated which skills were most in demand for AI jobs by using the list of keywords for AI skills and the dictionary() to construct a new dataframe using the keywords as keys and the frequencies of the skills within the dataset as the values. Created count_skill() function that passed in AI skills and a label_mapping dictionary to sum AI keyword labels together based on skill and account for the demand in AI skills that weren't controlled by the AI keywords term filter. Peformed comparative analysis on the demand for top twenty software skills, for AI and non-AI jobs to measure the degree of skills overlap in tech sector by applying a data mask. 

Performed analysis to determine the relative proportion of the job level required for AI positions to job level required for non-AI positions using the respective dataframe and calling the "job level" column. Investigated the difference in minimum years of experience between AI-related and general tech roles by parsing out years of experience from the posting and a regex heursitic to handle the repetition of certain text in the job description. Analyzed the national distribution of AI and Non_AI jobs by State using a list of State abbreviations and a get_location() function, as well as the proportional distribution of AI to non_AI jobs by State.

**Accesing the System**

---
## Results

### Findings

*AI Sectors and Profits*

* Technology as the primary AI sector / Manufacturing secondary:

    ![Number of Companies by Sector]()

    ![Profits by Sector]()

*Tech Workplace Flexibility and Job Levels:*

* Job Level and Job Type patterns:

    ![Job Type Distribution by State]()

    ![Top AI Skill per Job Level]()

*US Census Predictions:* 

* Percent in Tech Fields and No Education

* Percent in Tech Fields and High School Education

* Percent in Tech Fields and GED

* Percent in Tech Fields Professional Education

    ![Working in Tech Field vs Unemployment]()  

    ![Working in Tech Field with Professional Education]() 

* Prophet Predictions:

    ![Increased Employment and Professional Education in tech fields.]() 

*AI vs Non-AI Software Developers:* 

* Most AI jobs are in .... and require the foollowing skillset 
    
    ![Tech Jobs by US State]() -
    
    ![AI vs Non-AI Job Distribution]() 

    ![AI Skills Demand]() 

    ![AI vs Non-AI Top 20 Skills]() 

### Lingering Questions
 * To explore later: AI in manufacturing jobs, more job level granularity.
___
## Limitations

**US Census Predictions:** The classification of tech-related jobs was the closest representation to the ML workforce based on the needs of the project.

**AI vs Non-AI Software Developers:** The raw LinkedIn job postings dataset did not include a years of experience in an isolated, instead it was included in the job description. Given the irregularity of the summary texts, there was no guarantee all information was correctly extracted. 

## Conclusion

* Summarize the project, include limitations, repeat thesis, discuss what was proven and what requires further analysis.

## Workpapers in GitHub

**Visualizations Format:** <img src='' title='AI Skills' alt='A display of 6-8 AI related visualizations.'/>

## References/Footnotes

[^1]: [AI vs ML Definition](https://www.simplilearn.com/rise-of-ai-and-machine-learning-job-trends-article)