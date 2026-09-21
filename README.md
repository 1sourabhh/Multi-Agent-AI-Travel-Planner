# ✈️ Multi-Agent AI Travel Planner

An AI-powered travel planning application built with **LangGraph** and **LLMs** to generate personalized travel plans using multiple specialized AI agents.

The system searches for flights and hotels, creates an itinerary, and produces a final travel plan by combining the results from different agents.

## 🚀 Features

* 🤖 **Multi-Agent Architecture** using LangGraph
* ✈️ **Flight Search Agent** for finding flight information
* 🏨 **Hotel Search Agent** using Tavily web search
* 🗺️ **Itinerary Agent** for creating a personalized travel itinerary
* 🧠 **Final Planning Agent** that combines all results
* 💾 **PostgreSQL Checkpointing** for LangGraph state persistence
* ⚡ **Groq LLM** for fast AI responses
* 🌐 **Tavily Search API** for real-time web information
* 🎨 **Streamlit UI** for an interactive interface

## 🏗️ Architecture

```text
                 User Travel Request
                         │
                         ▼
                 ┌───────────────┐
                 │ Flight Agent  │
                 └───────┬───────┘
                         │
                         ▼
                 ┌───────────────┐
                 │ Hotel Agent   │
                 └───────┬───────┘
                         │
                         ▼
                 ┌──────────────────┐
                 │ Itinerary Agent  │
                 └────────┬─────────┘
                          │
                          ▼
                 ┌──────────────────┐
                 │  Final Agent     │
                 └────────┬─────────┘
                          │
                          ▼
                    Final Travel Plan
```

## 🛠️ Tech Stack

* **Python**
* **LangGraph**
* **LangChain**
* **Groq**
* **Tavily Search API**
* **PostgreSQL**
* **Psycopg**
* **Streamlit**
* **python-dotenv**

## 📁 Project Structure

```text
multi-agent-langgraph/
│
├── main.py
├── frontend.py
├── requirements.txt
├── README.md
│
└── tools/
    ├── __init__.py
    ├── tavily_tool.py
    └── flight_tool.py
```

## 🔄 How It Works

### 1. Flight Agent

Receives the user's travel request and searches for relevant flight information.

### 2. Hotel Agent

Uses the **Tavily Search API** to find relevant hotels based on the destination and travel requirements.

### 3. Itinerary Agent

Uses the flight and hotel information along with the user's request to generate a structured travel itinerary.

### 4. Final Agent

Combines all the collected information and generates the final travel plan for the user.

### 5. PostgreSQL Checkpointing

LangGraph state is persisted using PostgreSQL through `PostgresSaver`, allowing the application to maintain graph execution state.

## 🔑 Environment Variables

Create a `.env` file for local development:

```env
GROQ_API_KEY=your_groq_api_key
TAVILY_API_KEY=your_tavily_api_key
DATABASE_URL=your_postgresql_connection_string
```

For Streamlit Cloud, add these values under:

**App → Settings → Secrets**

Example:

```toml
GROQ_API_KEY = "your_groq_api_key"
TAVILY_API_KEY = "your_tavily_api_key"
DATABASE_URL = "your_postgresql_connection_string"
```

> Never commit API keys, passwords, or database credentials to GitHub.

## ▶️ Run Locally

Clone the repository:

```bash
git clone https://github.com/1sourabhh/multi-agent-langgraph.git
cd multi-agent-langgraph
```

Create and activate a virtual environment:

```bash
python -m venv venv
```

Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Add your environment variables to `.env`.

Then run the Streamlit application:

```bash
streamlit run frontend.py
```

## ☁️ Deployment

The application can be deployed using **Streamlit Community Cloud**.

Required configuration:

* GitHub repository
* `GROQ_API_KEY`
* `TAVILY_API_KEY`
* Cloud PostgreSQL `DATABASE_URL`

## 🎯 Example Request

```text
Plan a 5-day trip from Delhi to Dubai for 2 people.
Find suitable flights and hotels and create a day-wise itinerary.
```

The system processes the request through the different agents and returns a consolidated travel plan.

## 🔮 Future Improvements

* Real-time flight API integration
* Real-time hotel booking APIs
* Budget optimization
* Weather-aware itinerary planning
* Map integration
* Multi-destination trip planning
* MCP-based travel tools
* Personalized travel preferences and memory

## 👨‍💻 Author

**Sourabh Yadav**

B.Tech Computer Science & Engineering

GitHub: https://github.com/1sourabhh

LinkedIn: https://linkedin.com/in/sourabh-yadav-536a08224

```
```
