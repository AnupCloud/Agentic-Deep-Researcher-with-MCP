# Agentic Deep Researcher

A multi-agent research assistant powered by CrewAI, LinkUp, and Streamlit. This app enables deep web research using agentic AI workflows, with a user-friendly chat interface.

---

## Features

- Multi-agent orchestration using CrewAI (Web Searcher, Research Analyst, Technical Writer)
- Deep web search via LinkUp API
- Streamlit-based interactive chat UI
- Enterprise-ready, extensible, and easy to deploy

---

## Setup Instructions

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd mcp_research
```

### 2. Install `uv` (if not already installed)
[`uv`](https://github.com/astral-sh/uv) is a fast Python package installer and resolver.

```bash
pip install uv
```

### 3. Install Dependencies
Use `uv` to install all required packages from `requirements.txt`:

```bash
uv pip install -r requirements.txt
```

### 4. Set Up Environment Variables
The app requires a LinkUp API key for web search. You can provide this in two ways:

- **Recommended:** Enter your API key in the Streamlit sidebar when prompted.
- **Alternatively:** Create a `.env` file in the project root or `src/` directory:

```
LINKUP_API_KEY=your_linkup_api_key_here
```

### 5. Run the Streamlit App
From the project root, launch the app with:

```bash
streamlit run src/app.py
```

Or, using the absolute path (as per your example):

```bash
streamlit run /Users/coschool/Desktop/Anup/project/mcp_research/src/app.py
```

---

## Usage

1. Open the app in your browser (Streamlit will provide a local URL).
2. Enter your LinkUp API key in the sidebar (or ensure it is set in your environment).
3. Start chatting! Ask research questions and receive structured, cited answers.

---

## Project Structure

```
mcp_research/
│
├── requirements.txt
├── src/
│   ├── app.py         # Streamlit UI
│   ├── agents.py      # CrewAI agent orchestration
│   └── ...            # Other modules
└── ...
```

---

## Cursor IDE Integration

To enable custom MCP server integrated with cursor IDE use `.json` file and add in the MCP.

```json
{
  "mcpServers": {
  "crew_research": {
      "command": "uv",
      "args": [
        "--directory",
        "/Users/coschool/Desktop/Anup/project/mcp_research/src",
        "run",
        "server.py"
      ],
      "env": {
        "LINKUP_API_KEY": "aa461445-eef6-42d4-8bb5-e68735da0b71"
      }
    }
  }
}
```

**Instructions:**
1. Copy the above JSON.
2. Create a file named `.cursor.json` in your project root.
3. Paste the JSON content and update any values (like your API key) as needed.

---

## Troubleshooting

- **Missing API Key:** If you see a prompt for the LinkUp API key, enter it in the sidebar.
- **Dependency Issues:** Ensure you used `uv pip install -r requirements.txt` and are using Python 3.11+.
- **Port Conflicts:** If Streamlit fails to launch, try specifying a different port:  
  `streamlit run src/app.py --server.port 8502`

---

## Credits

- [CrewAI](https://github.com/joaomdmoura/crewai)
- [LinkUp](https://linkup.so/)
- [Streamlit](https://streamlit.io/)

---

## License

MIT License
