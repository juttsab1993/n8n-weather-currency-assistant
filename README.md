# AI Weather & Currency Assistant

A chat-based assistant built with n8n that checks current weather and converts currencies using API data.

I built this project to practice AI tool selection, API integration, and conversation memory.

## What it does

* Looks up current weather by city using OpenWeatherMap.
* Fetches exchange rates using ExchangeRate-API.
* Converts amounts between supported currencies.
* Uses Simple Memory to understand follow-up questions within a chat session.

## How it works

The Chat Trigger receives a message. An AI Agent connected to a Groq Chat Model selects the relevant tool, retrieves the data, and writes a short response.

The weather tool returns current conditions. The currency tool returns exchange rates, which the agent uses to calculate the converted amount.

## Tools used

n8n · Groq Chat Model · OpenWeatherMap · HTTP Request · ExchangeRate-API · Simple Memory

## Example requests

* “Lahore ka current weather batao.”
* “100 USD ko PKR mein convert karo.”
* “Jis shehar ka abhi poocha tha, uska naam kya hai?”

## Tested

* Weather lookup for Lahore.
* Recall of the previously mentioned city.
* Currency tool receiving the correct base currency code.
* A USD-to-PKR conversion checked against the full API rate.

## Current limitations

* Weather results show current conditions, not forecasts.
* Exchange rates follow the API’s update schedule, not live market pricing.
* Simple Memory provides session context, not permanent chat storage.
* Currency arithmetic is currently handled by the AI model; a dedicated calculation step is a future improvement.
