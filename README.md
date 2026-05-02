# 📄 Local AI Resume Optimizer

A **privacy-first** Streamlit application that uses Ollama to optimize your resume for Applicant Tracking Systems (ATS) and specific job descriptions. All processing happens locally on your machine—**your data never leaves your computer!**

## ✨ Features

- **🔒 100% Private**: All AI processing runs locally via Ollama (no cloud, no servers)
- **🎯 ATS Scoring**: Calculate an ATS score comparing your resume against job keywords
- **🔍 Keyword Extraction**: Automatically identifies required skills from job descriptions
- **✍️ Smart Rewriting**: Rewrites resume bullets naturally while incorporating missing keywords
- **📊 Before/After Comparison**: See your score improvement and review side-by-side changes
- **🎛️ Model Selection**: Choose any Ollama model you've installed (llama3.2, mistral, phi3, etc.)
- **🚀 Zero Setup**: Uses Python's built-in Streamlit for instant web UI

## 🚀 Quick Start

### Prerequisites

1. **Install Ollama**: Download from https://ollama.com
2. **Install Python 3.9+**: Ensure you have Python installed
3. **Pull a Model** (run once):
   ```bash
   ollama pull llama3.2
   ```
   *(Lighter alternative: `ollama pull phi3` or `ollama pull mistral`)*

### Installation

1. Clone/navigate to this directory:
   ```bash
   cd day7-local-ai-resume-optimizer-app
   ```

2. Create a virtual environment (optional but recommended):
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Run the App

1. **Start Ollama** (if not already running):
   ```bash
   ollama serve
   ```
   *(Keep this terminal open)*

2. **Run the app** (in a new terminal):
   ```bash
   streamlit run app.py
   ```

3. Open your browser to: **http://localhost:8501**

## 📋 How It Works

The app optimizes your resume in **3 automatic steps**:

### Step 1: Extract Keywords
- Reads the job description you provide
- Identifies key technical skills, tools, certifications, and requirements
- Creates a list of must-have keywords

### Step 2: Score Your Resume
- Compares your resume against the extracted keywords
- Calculates an **ATS score** (0–100%)
- Identifies **missing keywords** that should be added

### Step 3: Optimize & Rewrite
- Asks the AI to rewrite your resume bullets naturally
- Incorporates missing keywords where relevant
- Preserves job titles, companies, dates, and accuracy
- Recalculates your score to show improvement

## 💡 Usage Tips

1. **Paste Your Resume**: Include your full resume with job titles, companies, dates, and bullet points
2. **Paste the Job Description**: Copy the entire job posting from LinkedIn, Indeed, or company website
3. **Select a Model**: 
   - `llama3.2` (recommended, good balance)
   - `llama3.1:8b` (slower but more accurate rewrites)
   - `mistral` (fast, lightweight)
   - `phi3` (smallest, good for older machines)
4. **Review the Output**: Always proof-read the optimized resume—AI sometimes rephrases oddly
5. **Keep It Truthful**: Only keep rewrites that accurately describe your actual experience
6. **Tailor Per Job**: Run this for every job application to maximize relevance

## 📊 Understanding Your Score

- **🔴 Below 50%**: Resume is missing critical keywords; major revision needed
- **🟡 50–69%**: Resume has some keywords but missing key terms; good opportunity to improve
- **🟢 70%+**: Resume is well-aligned with the job; ready to submit

> **Note**: ATS scoring is approximate. The real score depends on each company's ATS system and how they weigh different keywords.

## 🔧 Configuration

Inside `app.py`, you can adjust these parameters in the `call_ollama()` function:

| Parameter | Default | Purpose |
|-----------|---------|---------|
| `temperature` | 0.0 | Deterministic output (0 = no randomness; 1 = creative) |
| `num_ctx` | Varies | Context window (how much text the model "remembers") |
| `num_predict` | Varies | Max tokens to generate in response |

For more creative rewrites, increase `temperature` to `0.3–0.5`. For consistency, keep it at `0.0`.

## ❌ Troubleshooting

| Issue | Solution |
|-------|----------|
| **"Cannot reach Ollama"** | Run `ollama serve` in a separate terminal |
| **"No models found"** | Pull a model: `ollama pull llama3.2` |
| **App runs slowly** | Use a smaller model (`phi3`, `mistral`) or reduce `num_ctx` in `call_ollama()` |
| **Streamlit shows "Address already in use"** | Ollama or Streamlit already running; check `lsof -i :8501` or `lsof -i :11434` |
| **Poor-quality rewrites** | Use a larger model (`llama3.1:8b`) or provide more detailed resume/job description |
| **Resume didn't change much** | High existing score = already optimized. Try a different job posting. |

## 📦 Requirements

See `requirements.txt`:
- **streamlit**: Web UI framework
- **ollama**: Python client for local Ollama server

Install with:
```bash
pip install -r requirements.txt
```

## 🏗️ Project Structure

```
day7-local-ai-resume-optimizer-app/
├── app.py              # Main Streamlit application
├── requirements.txt    # Python dependencies
└── README.md          # This file
```

### Key Functions in `app.py`

| Function | Purpose |
|----------|---------|
| `get_available_models()` | Fetches list of installed Ollama models |
| `extract_keywords()` | Uses AI to extract job keywords |
| `score_resume()` | Calculates ATS score and finds missing keywords |
| `rewrite_resume()` | Uses AI to optimize resume bullets |
| `optimize_resume()` | Orchestrates all 3 steps |
| `normalize()` | Normalizes text for fair keyword matching |

## 🎓 Learning Resources

- **Ollama Docs**: https://github.com/ollama/ollama
- **Streamlit Docs**: https://docs.streamlit.io
- **Available Models**: https://ollama.com/library

## 🔐 Privacy & Security

- ✅ **All processing is local** — no data sent to external servers
- ✅ **No API keys needed** — runs entirely on your machine
- ✅ **No tracking** — Streamlit runs in your browser
- ✅ **No data retention** — nothing is stored after you close the app

## 💬 Tips for Best Results

1. **Use detailed resumes** — More context = better rewrites
2. **Use focused job descriptions** — Copy the full posting, not just a summary
3. **Review outputs carefully** — AI can sometimes invent details or rephrase awkwardly
4. **Maintain your brand** — Don't change your core accomplishments, just rephrase them
5. **Test with multiple jobs** — Different roles need different optimizations

---

**Built with ❤️ using Streamlit + Ollama**
