# AI News Impact Generator (n8n Automation)

An automated **AI-powered news processing pipeline** built using **n8n, NewsData API, and Gemini AI**.
The workflow fetches trending global news, analyzes the article using AI, and generates **profession-specific news summaries** highlighting the impact on different industries.

The final output is structured and stored in **Supabase** and exported as a **CSV dataset**, which can be displayed or used for further analysis.

---

# Project Overview

This project automates the process of:

1. Fetching trending news from a news API.
2. Extracting the article content.
3. Using AI to rewrite the news from the perspective of different professions.
4. Structuring the results into a dataset.
5. Saving the processed data to a database.

Instead of simply summarizing news, the system produces **journalist-style headlines and short articles tailored to different industries**, helping professionals quickly understand how global events may impact their work.

---

# Technologies Used

* **n8n** – Workflow automation
* **NewsData.io API** – Fetch latest news articles
* **Gemini AI** – Generate profession-specific articles
* **Supabase** – Store structured data
* **GitHub** – Host workflow and dataset

---

# Workflow Architecture

The automation pipeline works as follows:

Schedule Trigger
⬇
News Category Selector
⬇
HTTP Request (NewsData API)
⬇
AI Agent (Gemini)
⬇
Separator / Parser
⬇
Supabase Note Node
⬇
Dataset Export (CSV)

---

# How It Works

### 1. Schedule Trigger

The workflow runs automatically on a schedule to fetch new news articles.

### 2. Category Selection

A news category such as:

* World
* Geopolitics
* Technology
* Economy

is selected dynamically.

### 3. News API Request

The workflow calls the **NewsData.io API** to fetch the latest article in the chosen category.

### 4. AI Article Processing

The article URL is sent to the **AI Agent**, which:

* Reads the article
* Extracts key information
* Writes short journalist-style articles tailored to different professions.

### 5. Profession-Specific News

AI generates **5 versions of the same news story** for:

* Agriculture & Allied Activities
* Retail Trade & Small Business
* Manufacturing
* Education
* Construction

Each version includes:

* A headline
* A short ~60 word article
* Industry-specific relevance.

### 6. Separator Node

Because AI sometimes returns different text formats, a **custom JavaScript separator node** extracts each profession's article reliably.

### 7. Supabase Note Node

The processed news is stored in **Supabase**, allowing it to be queried or displayed in other applications.

### 8. CSV Dataset Export

The structured output is exported as a **CSV file** and committed to this repository.

---

## Example Output

Below is an example of the processed AI-generated news output.

| Agriculture & Allied Activities                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Retail Trade & Small Business                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Manufacturing                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | Education                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | Construction                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Headline:** Global Focus on Climate Resilience Benefits Agricultural Sector  <br><br> **Article:** Helen Clark's reflections highlight the need for climate change adaptation, especially for Small Island Developing States. This renewed focus is expected to encourage investment in climate-smart farming technologies, improved resource management, and diversified agricultural practices. Farmers and related businesses may benefit from stronger food systems and more resilient agricultural supply chains. | **Headline:** Economic Diversification & Digital Uplift Boost Retail Outlook  <br><br> **Article:** Helen Clark’s emphasis on economic diversification and improved digital connectivity for island nations creates opportunities for retail and small businesses. Expanding digital infrastructure can improve market access, streamline operations, and support new consumer trends. These developments encourage innovation, allowing local businesses to grow in a more stable and resilient economic environment. | **Headline:** Push for Resilience Spurs Local Manufacturing Opportunities  <br><br> **Article:** Calls for stronger economic resilience and reduced reliance on global supply chains open new opportunities for the manufacturing sector. Countries are expected to invest more in local production and sustainable manufacturing. This shift can stimulate domestic industry growth, support job creation, and encourage innovation in producing goods closer to local markets. | **Headline:** Climate & Digital Skills Education Gains Urgency  <br><br> **Article:** Helen Clark’s reflections highlight the increasing importance of education in tackling global challenges like climate change and digital transformation. Educators are expected to focus more on developing critical thinking, sustainability awareness, and digital literacy skills. Schools and training institutions play a key role in preparing future generations to adapt to evolving global economic and environmental conditions. | **Headline:** Climate Adaptation Drives Demand for Resilient Construction  <br><br> **Article:** The growing emphasis on climate adaptation is expected to increase demand for resilient infrastructure and sustainable building practices. Construction companies may see new opportunities in projects designed to protect vulnerable communities from environmental risks. This includes climate-resilient housing, green infrastructure, and improved urban planning aimed at long-term sustainability. |

---

## CSV Output

The complete dataset generated by the workflow is stored in the repository as a CSV file.

`output/news_output.csv`


---

# CSV Output

The generated dataset can be found here:

`output/news_output.csv`

This file contains the structured results from the AI workflow.

Example structure:

| Agriculture_and_Allied_Activities | Small_Business | Manufacturing | Education    | Construction |
| --------------------------------- | -------------- | ------------- | ------------ | ------------ |
| Article text                      | Article text   | Article text  | Article text | Article text |

---

# Use Cases

This project can be used for:

* Industry focused news dashboards
* AI generated business intelligence
* Economic trend monitoring
* Professional newsletters
* Automated content pipelines

---

# Future Improvements

Possible improvements include:

* Multi-language news generation
* Daily automated GitHub commits
* AI credibility scoring
* News sentiment analysis
* Dashboard visualization

---

# Author

Built as an **AI + Automation project using n8n workflows** to demonstrate how news intelligence can be automated and tailored to professional sectors.
