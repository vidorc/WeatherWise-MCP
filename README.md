WeatherWise MCP: Real-Time Weather for AI Agents
📖 Overview
WeatherWise MCP is a lightweight Model Context Protocol (MCP) server that enables AI assistants and agents to retrieve and interpret real-time weather data. It acts as a bridge between a large language model and a live weather data source, allowing users to ask for the current weather in natural language.

This server is designed to be simple, efficient, and easy to integrate with any MCP-compatible client, such as a local AI agent or a desktop assistant. It uses the free and open-source Open-Meteo API, which does not require an API key for non-commercial use.

🎯 Core Functionality
The server exposes a simple get_weather tool that an AI agent can use. The process is as follows:

Geocoding: Converts a city name provided by the user into geographical coordinates (latitude and longitude).

API Request: Fetches current weather conditions from the Open-Meteo API using these coordinates.

Structured Response: Returns the weather data (temperature, wind speed, etc.) to the AI agent in a structured JSON format for easy processing.

✨ Features
Real-Time Weather: Provides up-to-the-minute weather data for any location globally.

No API Key Required: Leverages the Open-Meteo API, which is free for non-commercial use without an API key.

Seamless Integration: Works with any AI agent or application that supports the Model Context Protocol.

Lightweight & Fast: Designed for minimal resource consumption and quick response times.

Easy to Deploy: Can be run locally with a simple Python command.

💻 Technologies Used
Python

MCP SDK (mcp library): To create the MCP server and define the tools.

httpx or requests: For making HTTP requests to the weather API.

Open-Meteo API: As the source for weather data.

🚀 Getting Started
Prerequisites
Ensure you have Python (3.9 or newer) installed on your system.

Installation
Clone the repository:

git clone https://github.com/your-username/WeatherWise-MCP.git

Navigate to the project directory:

cd WeatherWise-MCP

Install the required Python libraries:

pip install mcp httpx

Running the Server
Start the server from your terminal:

python weather_server.py

Your MCP server will now be running and ready to accept requests from a connected AI agent.

🛠️ How It Works
Tool Definition: The server defines a tool named get_weather that accepts a city as a required parameter.

AI Agent Request: When a user asks an AI agent, "What's the weather in London?", the agent identifies that it needs to use the get_weather tool and calls the WeatherWise MCP server.

Data Fetching:

The server first makes a request to a geocoding service to get the latitude and longitude for "London".

It then uses these coordinates to make a second request to api.open-meteo.com to fetch the current weather data.

Structured Return: The server returns a JSON object to the agent, for example:

{
  "temperature": 15.5,
  "wind_speed": 12.3,
  "weather_code": 3
}

Final Response: The AI agent uses this structured data to formulate a natural language response for the user, such as "The current temperature in London is 15.5°C with a wind speed of 12.3 km/h."

⚖️ Disclaimer
For Informational Use: The weather data provided by this server is for informational purposes only.

Data Accuracy: The accuracy of the weather information is entirely dependent on the Open-Meteo API. There are no guarantees of correctness.

Rate Limiting: While the API is free, be mindful of fair use and potential rate limits imposed by the service provider.
