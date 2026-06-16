# Blog Writing Agent

A production-oriented AI Blog Writing Agent built with LangGraph, Google Gemini, and Streamlit.

## Overview

This project automates the end-to-end process of technical blog creation through a graph-based workflow. The system can:

- Analyze a topic and determine whether external research is required.
- Collect and synthesize supporting evidence.
- Generate a structured blog plan.
- Create section content in parallel using worker nodes.
- Merge content into a complete article.
- Plan and generate supporting images.
- Export blog content as Markdown with downloadable assets.

The application includes a Streamlit interface for generating, reviewing, and exporting blogs.

## Architecture

The workflow is implemented using LangGraph and follows a multi-stage pipeline:

1. Router
   - Determines whether the topic requires research.
   - Selects operating mode:
     - Closed Book
     - Hybrid
     - Open Book

2. Research
   - Performs external evidence gathering.
   - Filters and structures research results.

3. Orchestrator
   - Creates a detailed blog plan.
   - Defines sections, goals, and writing requirements.

4. Workers
   - Generate blog sections in parallel.
   - Support citations and code examples when required.

5. Reducer
   - Merges generated content.
   - Plans visual assets.
   - Generates and inserts images.
   - Produces the final Markdown output.

## Features

- LangGraph-based workflow orchestration
- Parallel content generation
- Automated research routing
- Evidence-aware writing
- Markdown export
- AI-generated diagrams and illustrations
- Streamlit web interface
- Blog history management
- Downloadable image bundles

## Technology Stack

### Backend

- Python
- LangGraph
- LangChain
- Google Gemini 2.5 Flash
- Tavily Search
- Pydantic

### Frontend

- Streamlit
- Pandas

## Project Structure

```text
.
├── bwa_backend.py
├── streamlit_app.py
├── images/
├── .env
├── requirements.txt
└── README.md
```

## Environment Variables

Create a `.env` file:

```env
GOOGLE_API_KEY=****
TAVILY_API_KEY=****
```

## Installation

```bash
git clone https://github.com/arshpreetw11/blog_writing_agent.git
cd blog-writing-agent

python -m venv venv

# Windows
venv\Scripts\activate

# Linux / macOS
source venv/bin/activate

pip install -r requirements.txt
```

## Running the Application

```bash
streamlit run streamlit_app.py
```

Open the URL displayed in the terminal to access the interface.

## Workflow Modes

### Closed Book

Used for evergreen topics that do not require external research.

### Hybrid

Combines model knowledge with fresh external evidence.

### Open Book

Used for news, recent developments, policy changes, pricing updates, and other time-sensitive topics.

## Output

The system generates:

- Structured Markdown blog posts
- Embedded image references
- Downloadable image archives
- Complete blog bundles (Markdown + images)

## GitHub

Repository Owner: **arshpreetw11**

GitHub Profile:
https://github.com/arshpreetw11

## License

MIT License

## Acknowledgements

Built using:

- LangGraph
- LangChain
- Google Gemini
- Streamlit
- Tavily Search
