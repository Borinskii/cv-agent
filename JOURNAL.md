# Project Journal



## Step 1 – 24.04.2025

### System Description and Goal

The planned system is a CV–Job Match Agent - a CLI tool that takes a candidate's CV (PDF or plain text) and a job posting URL, and produces a structured report with a fit score, matched skills, and identified gaps. The core idea is to go beyond simple matching: the system suggests concrete ways to refactor and fine-tune the existing CV to better align with the specific job requirements - rewording experience, surfacing relevant skills, and flagging what is missing. The goal is to replace manual CV-to-job comparison with an automated, semantically-aware analysis that gives actionable editing advice.

### AI and Agent-Based Approach

The system is implemented as a single intelligent agent that executes a fixed pipeline of tool calls. The AI component handles two reasoning steps: extracting structured skill lists from raw text, and performing semantic gap analysis that goes beyond simple keyword matching. This is necessary because purely rule-based matching fails on synonyms and paraphrasing (e.g. "ML" vs "machine learning"). The LLM backend is Fireworks AI with structured JSON prompting to keep outputs consistent between pipeline stages.



### Tools

- **PDF Parser** - extracts text from the CV file (`pdfplumber`)
- **Web Scraper** - fetches and cleans the job posting HTML (`requests` + `BeautifulSoup4`)
- **Skill Extractor** - LLM call that converts raw text from both documents into structured JSON skill lists
- **Gap Analyzer** - compares skill sets and computes a fit score
- **Report Generator** - formats the final output as a readable Markdown report



### Preliminary Programming Concepts

- File I/O and PDF parsing
- HTTP requests and HTML parsing
- REST API integration (Fireworks AI)
- JSON serialization and schema validation
- Modular project structure
- CLI argument parsing (`argparse`)
- Exception handling (network errors, malformed input)
- Unit testing with `pytest`
- Environment variable configuration