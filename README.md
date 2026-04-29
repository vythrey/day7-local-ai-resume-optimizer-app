# Local AI Resume Optimizer App

A Streamlit app that uses Ollama (local LLM) to optimize resumes for job applications. **No data leaves your machine!**

## Prerequisites

1. **Install Ollama**: https://ollama.com/download
2. **Pull a model**:
   ```bash
   ollama pull llama3.2:1b
   ```
3. **Start Ollama** (if not running):
   ```bash
   ollama serve
   ```

## Setup

1. Navigate to the project directory:
   ```bash
   cd day7-local-ai-resume-optimizer-app
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Run the App

```bash
streamlit run app.py
```

The app will open at http://localhost:8501

## Features

- **Local Processing**: All AI processing happens locally via Ollama
- **Keyword Analysis**: Identifies missing keywords from job descriptions
- **Resume Optimization**: Generates improved resume bullets
- **Multiple Model Support**: Choose from any Ollama model you have installed

## Troubleshooting

- **Ollama not running**: Start with `ollama serve`
- **No models found**: Pull a model with `ollama pull llama3.2:1b`
- **Port already in use**: Ollama is likely already running
