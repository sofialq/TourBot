# TourBot

**An agentic AI tour-planning assistant that designs fan-conscious touring routes**

## Overview

TourBot helps plan multi-city tour itineraries for artists and bands by reasoning about more than just geography. Built with Python, Streamlit, and the Claude API, it routes tours with awareness of festival schedules, local events, and where an artist's fanbase is mostly concentrated, with the goal of getting shows in front of more fans rather than just hitting the most geographically convenient cities.

## How it works

### Fan-conscious routing logic

Instead of optimizing a route purely on geographic proximity, TourBot factors in:

- **Fanbase density** — prioritizing cities and regions where an artist has a strong following
- **Proximity to nearby cities** — sequencing stops to minimize unnecessary travel between dates as well as allow fans who don't have a stop in their city to travel
- **Event conflicts** — checking for overlapping festivals, sporting events, and other major local events that could compete for audience attention

The goal is a tour that reaches more fans, minimizing the struggles fans may face when considering to buy concert tickets, such as scheduling conflicts and ability to travel.

### Multi-turn conversation memory

Tour planning evolves over a long back-and-forth as constraints get added, removed, or changed. TourBot maintains conversation memory across the full planning session, with auto-summarization that compresses earlier context so the assistant stays grounded in the full conversation history without losing track of prior decisions.

### Streamlit interface

- Sidebar inputs for tour parameters (cities, dates, constraints)
- Live chat interface for iterating on the plan conversationally
- Markdown export so a finished itinerary can be saved or shared outside the app

## Tech stack

- **Python**
- **Streamlit** — UI framework
- **Claude API** — powers the conversational planning agent

## Getting started

```bash
git clone https://github.com/sofialq/MUI402-Capstone.git
cd MUI402-Capstone
pip install -r requirements.txt
```

Create a `.streamlit/secrets.toml` file in the project root with your Anthropic API key:

```toml
ANTHROPIC_API_KEY = "your-api-key-here"
```

This file is gitignored, so you'll need to add your own key before running the app locally.

```bash
streamlit run streamlit_app.py
```

## Project background

Built as a capstone project bridging a Music Industry background with applied data science, exploring how AI tools can be leveraged to support more equitable, fan-aware tour planning.

## License

Apache-2.0
