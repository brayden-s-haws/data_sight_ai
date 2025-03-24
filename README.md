# Database AI Onboarding Tool

#### Current status: complete ####

## Description
This app allows users to quickly onboard themselves to the contents of a database or data warehouse.  It uses standard data tools and Generative AI agents to surface information about the data. Currently it offers:
* AI generated descriptions for each table
* Data preview and column stats
* AI generated table relationship details
* Natural language querying via an LLM-based agent (this agent is built with error handling and can recover from errors to generate a valid query)

(This is meant to be a proof of concept for how AI tools can help users better understand and work with their data.)


## How It Works
The app can be connected to SQL based databases or warehouses. The user is able to select the database they wish to work with, the table they are interested in, and the number of rows to preview. They are then shown several details about the data including a description of the table, how it relates to other tables, column fill stats and a data preview. Lastly, they can ask questions in natural language and an AI agent will generate SQL to answer those questions. The descriptions, relationships, and queries are all generated using [LangChain](https://www.langchain.com).

You can check out a demo [here](https://share.cleanshot.com/GLQQkmTy).

The app is hosted on [Hex](https://hex.tech) and your can test it for yourself at this [link](https://app.hex.tech/455658aa-ee04-480f-945a-3fd455933fa2/app/5674db16-661a-4545-916f-ffafe6620ea2/latest).

The code for this is available in several forms for both Postgres and BigQuery (files are appended with a bq or pq indicator):
* A jupyter notebook file that you can run on the configuration of your choice
* A yaml file that is meant for importing into Hex


## Acknowledgements
Huge thanks to Hex and Jordan East for the inspiration to use Hex as the basis for this tool, and their examples using [Langchain with Snowflake to build a Chatbot](https://hex.tech/use-cases/exploratory-analysis/text-SQL-chatbot/).

___

### Personal Progress ###
* What I learned: How to work with the LangChain framework for querying databases and integrating with foundation LLM model APIs.
* What I wish I had done differently: Not done this in a Jupyter notebook. It made for an easy frontend but really limited what functionality I could offer and made deploying a production quality version difficult to impossible. I had ideas for implementing things like ERD generation and AI generated charts but could not get them working in the notebook.
* What I am most proud of: Lines [579-638](https://github.com/brayden-s-haws/data_sight_ai/blob/8164b5b8f2aee8a0173579838ca5cc2998240310/pg_datasight_ai.yaml#L579) of pg_datasight_ai.yaml. It would have been easy to just generate a description each time the user inspected a table but by storing them we avoid excess usage of compute and drive consistency of definition across users.
