# Description
This app allows users to quickly onboard themselves to the contents of a database.  It uses standard data tools and Generative AI agents to surface information about the data. Currently it offers:
* AI generated descriptions for each table
* Data preview and column stats
* AI generated table relationship details
* Natural language querying via an LLM-based agent
(This is meant to be a proof of concept for how AI tools can help users better understand and work with their data.)


# How It Works
The app comes pre-loaded with a series of datasets. These datasets span domains (sales, search trends, churn, supply chain) and time intervals (daily, weekly, monthly, quarterly). The user is able to select the dataset they wish to work with and the number of intervals they would like to forecast. They then select the type of forecast(s) to run: linear, simple seasonal ([SARIMAX](https://towardsdatascience.com/time-series-forecasting-with-arima-sarima-and-sarimax-ee61099e78f6)), advanced seasonal ([Prophet](https://facebook.github.io/prophet/)). The app then does the work to determine the correct configuration for each forecast based on the selected dataset. It runs the forecast models and generates a chart with the outputs. The outputs can also be exported to csv or xlsx.

The app is hosted on [Hex](https://hex.tech) and your can test it for yourself at this [link](https://app.hex.tech/455658aa-ee04-480f-945a-3fd455933fa2/app/6356acb1-2d8d-4f12-96a9-376dac1bb85e/latest).

The code for this is available in two forms:
* A jupyter notebook file that you can run on the configuration of your choice
* A yaml file that is meant for importing into Hex

# Roadmap
Currently there are a limited number of datasets available. The code is written in a manner to handle any dataset with at least one series of values and a corresponding series of dates. I would like to add a way for users to be able to upload their own dataset and run forecasts on it.
