# Career agent (supervised)

## Setup on Windows (PowerShell)
1. python -m venv .venv, then activate it with the Activate.ps1 script in .venv\Scripts
2. pip install -r requirements.txt, then python -m playwright install msedge
3. Get a free key at Google AI Studio and set GEMINI_API_KEY in your shell.
4. Copy candidate.example.md to candidate.md and fill it from your verified resume only.
5. Run: python agent.py "Prepare the application for this role, stop before submit" --url "<job url>"

## What it will and won't do
- Opens a browser that keeps your sign-in locally. You log in and complete MFA.
- Reads labels, fills text and dropdowns, saves progress to ~/.career-agent/applications.jsonl.
- Refuses to fill password, OTP, card or bank fields.
- Stops on CAPTCHAs and bot checks and asks you to take over.
- Clicks anything that looks like Submit only after you type APPROVE.

## Status
Compiles and implements the full loop. Not yet tested against a live portal or the Gemini API.
Expect to adjust selectors for each portal (Amazon, Workday, Indeed) after the first real run.
Keep candidate.md, the records file and the browser profile out of git.
