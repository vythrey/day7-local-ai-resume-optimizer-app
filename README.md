# Local AI Resume Optimizer App

## Overview
This project is a Streamlit web app that compares a resume with a job description, estimates keyword alignment, and generates truthful optimized resume bullets using a local LLM through Ollama.

It combines:
- ATS-style keyword alignment scoring
- Local LLM-based resume rewriting
- Streamlit web interface

This project does not require a paid API.

## Features
- Paste job description and resume text
- Extract important requirements using a local LLM
- Estimate original resume keyword alignment score
- Generate optimized resume bullets
- Estimate optimized resume keyword alignment score
- Show before/after improvement
- Display missing or weakly matched areas
- Run locally without paid API keys

## Why I Built This
I built this project to turn my command-line AI agents into a simple portfolio-ready web app.

The goal is to learn how local LLMs can be combined with Python logic and a user interface to solve a practical career-related problem.

## Tech Stack
- Python
- Streamlit
- Ollama
- Llama 3.2 local model
- JSON parsing
- Regular expressions

## How It Works
1. User pastes a job description
2. User pastes resume content
3. The local LLM extracts important job requirements
4. Python calculates the original match score
5. The local LLM rewrites the resume bullets truthfully
6. Python calculates the optimized match score
7. The app displays scores, gaps, and optimized bullets


## Setup Instructions

### 1. Install Ollama
Download from:
https://ollama.com

---

### 2. Start Ollama server
```bash
ollama serve
```

### 3. Pull model
```bash
ollama pull llama3.2:1b
```

### 4. Install Python dependency
```bash
pip install ollama
```

### 5. Run the project
```bash
python3 day6_resume_optimizer.py
```
