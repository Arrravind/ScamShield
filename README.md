# ScamShield

ScamShield is an educational web prototype that checks user-pasted messages and URLs for a small set of common fraud warning signs using transparent rules.

## Features
- Checks for urgency, unexpected rewards, credential requests, and account-verification claims.
- Checks URLs for selected patterns such as plain HTTP, numeric hosts, encoded internationalized domains, and unusually long or hyphen-heavy domains.
- Explains detected warning signs and gives basic safety guidance.
- Runs locally without a paid API or sending submitted text to an external service.

## Requirements
- Python 3.10 or later
- Internet connection only to install Flask (not required for the checker itself after installation)

## Setup
```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS/Linux:
source .venv/bin/activate
pip install -r requirements.txt
python scamshield/app.py
```
Open `http://127.0.0.1:5000` in your browser.

## Test
```bash
python -m unittest discover -s tests -v
```

## Limitations and safety
This prototype is not a definitive malware, phishing, or reputation scanner. It does not visit URLs, inspect website content, use a trained machine-learning model, or query a threat-intelligence feed. Rule matches can produce false positives and false negatives. A result that reports no configured warning signs does not mean content is safe. Do not paste passwords, one-time passwords, bank details, or other private information.

## Environment variables
No environment variables are required for the local prototype.

## Project contents
- `scamshield/app.py`: Flask application and rule engine
- `tests/test_analyser.py`: automated rule checks
- `docs/TECHNICAL_DESIGN.md`: architecture and design notes
- `docs/DESIGN_NOTES.md`: user flow and wireframe description
- `docs/SAMPLE_TEST_CASES.md`: sample manual test cases
- `LICENSE`: MIT License

## Suggested next steps
Add usability testing with consent, Tamil-language rules, accessibility checks, and carefully sourced threat-intelligence data. Any future external lookups should be designed with privacy and security in mind.
