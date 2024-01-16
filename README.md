# Description
This app allows users to quickly onboard themselves to the contents of a database.  It uses standard data tools and Generative AI agents to surface information about the data. Currently it offers:
* AI generated descriptions for each table
* Data preview and column stats
* AI generated table relationship details
* Natural language querying via an LLM-based agent (this agent is built with error handling and can recover from errors to generate a valid query)
(This is meant to be a proof of concept for how AI tools can help users better understand and work with their data.)


# How It Works
The app comes pre-loaded with a series of BigQuery datasets. The user is able to select the dataset they wish to work with, the table they are interest in, and the number of rows to preview. They are then shown several details about the data including a description of the table, how it relates to other tables, column fill stats and a data preview. Lastly, they can ask questions in natural language and an AI agent will generate SQL to answer those questions. The descriptions, relationships, and queries are all generated using [LangChain](https://www.langchain.com).

You can check out a demo [here](https://share.cleanshot.com/dHzhQz3S).

The app is hosted on [Hex](https://hex.tech) and your can test it for yourself at this [link](https://app.hex.tech/455658aa-ee04-480f-945a-3fd455933fa2/app/9f3e2ca6-e2d9-4be5-b2b1-d761a410618b/latest).

The code for this is available in two forms:
* A jupyter notebook file that you can run on the configuration of your choice
* A yaml file that is meant for importing into Hex

# Roadmap
Currently we are using the most basic version of Langchain agents. We will be updating this to use advanced style agents which will allow us to offer:
* AI generated ERDs
* AI recommended visualizations

# Acknowledgements
Huge thanks to Hex and Jordan East for the inspiration to use Hex as the basis for this tool, and their examples using [Langchain with Snowflake to build a Chatbot](https://hex.tech/use-cases/exploratory-analysis/text-SQL-chatbot/).
