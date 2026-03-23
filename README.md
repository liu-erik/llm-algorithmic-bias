# The Coded Gaze Project

> *"We are all more than the worst thing we have ever done."*
> — Joy Buolamwini, Unmasking AI

## What This Is

An open audit tool that sends identical prompts to multiple large language models — ChatGPT, Gemini, and Claude — swapping one demographic detail at a time (a name, a race, a neighborhood) and measuring how their responses differ.

The goal is simple: make algorithmic bias visible to anyone, not just the researchers who study it.

## Why I Built This

I had no idea algorithmic bias existed until I read Joy Buolamwini's *Unmasking AI* in an information science course. Then I couldn't un-see it.

Robert Williams was wrongfully arrested in his driveway because a facial recognition algorithm misidentified his face. LaToya Smith died from melanoma partly because AI dermatology tools were trained on predominantly white skin. Joy Buolamwini herself — a CS undergraduate at MIT — discovered her face wasn't detected by a robot she was programming unless she held a white mask to the camera.

These aren't isolated failures. They're the same problem appearing across every domain where AI makes decisions about people — and the people being failed are almost never the people who were in the room when the system was built.

The most powerful thing CS can do right now isn't more innovation. It's accountability for the innovation that already exists.

## What It Does

- Sends a prompt to 3 major LLMs simultaneously
- Swaps one demographic variable per test (name, race, described appearance, location)
- Scores each response using sentiment analysis, keyword frequency, and response length
- Generates a bias score showing how differently each model treated each demographic group
- Archives every audit run — building a growing public dataset of LLM bias evidence

## Inspired By

- Joy Buolamwini & Timnit Gebru — [Gender Shades (2018)](http://gendershades.org)
- ProPublica — [Machine Bias (2016)](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing)
- Joy Buolamwini — *Unmasking AI* (2023)

## Status

**Currently in research phase** — reading, designing methodology, writing test prompts.

Build starts March 2026.

## Tech Stack (planned)

- Python + FastAPI (backend)
- React (frontend)
- VADER sentiment analysis (bias scoring)
- OpenAI, Google Gemini, Anthropic APIs
- PostgreSQL (results archive)
- Deployed on Vercel + Railway

## Project Structure (coming soon)

```
coded-gaze/
├── backend/
│   ├── main.py          # FastAPI app
│   ├── auditor.py       # Core prompt engine
│   ├── scorer.py        # Bias scoring (VADER + keywords)
│   └── database.py      # Results archive
├── frontend/
│   └── src/
│       └── App.jsx      # React interface
├── prompts/
│   └── prompts.json     # Test prompt library
└── research/
    └── notes.md         # Research notes and methodology
```
---

*Built by a CS student who had no idea algorithmic bias existed until one book changed that. Now building the tool that gives everyone else that same moment.*
