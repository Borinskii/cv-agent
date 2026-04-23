# CV-Job Match Agent

A command-line AI agent that analyzes a candidate's CV against a job posting and produces a structured report — including a fit score, matched and missing skills, and **concrete suggestions on how to rewrite and fine-tune the CV** to better align with the role.

## What it does

1. Parses your CV (PDF or `.txt`)
2. Scrapes and cleans the job posting from a URL
3. Extracts structured skill sets from both documents using an LLM
4. Computes a fit score and identifies skill gaps
5. Generates specific, actionable CV editing recommendations — what to reword, what to highlight, and what is genuinely missing

## Usage

```bash
python main.py --cv path/to/cv.pdf --job https://example.com/job-posting
```

## Setup

```bash
git clone https://github.com/Borinskii/cv-agent
cd cv-job-match-agent
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env      # add your Fireworks AI API key
python main.py --cv path/to/cv.pdf --job https://example.com/job-posting
```

## Project Structure

```
cv-job-match-agent/
├── main.py                 # Entry point and agent orchestration
├── tools/
│   ├── pdf_parser.py       # CV text extraction
│   ├── scraper.py          # Job posting web scraper
│   ├── skill_extractor.py  # LLM-based skill extraction
│   ├── gap_analyzer.py     # Skill comparison and fit score
│   └── report_generator.py # CV rewrite suggestions and final report
├── tests/
│   ├── test_pdf_parser.py
│   ├── test_scraper.py
│   ├── test_skill_extractor.py
│   └── test_gap_analyzer.py
├── requirements.txt
├── .env.example
├── JOURNAL.md
└── README.md
```

## Environment Variables

| Variable | Description |
|---|---|
| `FIREWORKS_API_KEY` | Your Fireworks AI API key — get one at [fireworks.ai](https://fireworks.ai) |

## Requirements

- Python 3.10+
- See `requirements.txt` for full dependency list

## Journal

Development progress is tracked in [`JOURNAL.md`](./JOURNAL.md), updated at each submission stage.
