# CRM AI Agent — Gemini + HubSpot

A small read-only prototype that lets you ask natural-language questions about HubSpot deals using Google's Gemini API.

## 1. Requirements

- Python 3.10 or newer
- A Gemini API key: https://aistudio.google.com/apikey
- A HubSpot private app access token with permission to read deals (`crm.objects.deals.read`)

## 2. Set up

Open Terminal and move into this project folder. Then run:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

On Windows, activate the environment with:

```powershell
.venv\\Scripts\\activate
```

## 3. Add your API keys

Copy `.env.example` and name the copy `.env`.

On macOS/Linux:

```bash
cp .env.example .env
```

Open `.env` in a text editor and replace the placeholder values with your real keys. Do not share your `.env` file or commit it to Git.

## 4. Run the agent

```bash
python main.py
```

Type `test` to check whether HubSpot can be reached. Then try questions such as:

- `Show me all our deals.`
- `Which deal has the highest amount?`
- `Summarise our sales pipeline.`
- `Which deals have the earliest closing dates?`

Type `exit` to close the program.

## Notes

- This prototype reads up to 100 HubSpot deals per request.
- It is read-only; it does not create or update CRM records.
- Deal-stage values may appear as HubSpot's internal stage IDs.
- If you get a 401 error, check the HubSpot token. If you get a 403 error, check the private app's scopes.
- Never put API keys directly into `main.py` or share them in screenshots.
