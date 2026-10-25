# SiteSense AI: Smart Construction Monitoring & Estimation Suite

SiteSense AI helps construction teams review site conditions, spot structural problems early, and plan budgets in Indian rupees, all from one Streamlit dashboard powered by Google Gemini.

🔗 **Try it live:** https://multimodal-construction-g36vs2mf5fzeewugtssuba.streamlit.app/

---

## Why this project

Site inspections are slow, and early warning signs such as missing helmets, unprotected edges and hairline cracks are easy to miss. SiteSense AI turns a photo into a structured, reviewable report in seconds, and combines that with quick cost and weather guidance for daily planning.

## What you can do with it

**1. Inspect a site photo**
Upload an image and the app counts workers, checks helmets, vests, boots and harnesses, and lists visible hazards ranked from Low to Critical, each with a suggested fix. You also get an overall safety score and a downloadable JSON report.

**2. Diagnose a cracked surface**
Upload a wall or concrete photo to get the likely defect type, an estimated crack width in mm, the probable causes, suggested repairs, and how urgently to act.

**3. Estimate cost and value**
Choose the building type, area, city tier and construction progress. The app returns the total budget, money spent so far, current and final property value in Lakh/Crore, material quantities, and a milestone tracker. It can also generate a concept image of the building.

**4. Plan the day around the weather**
Select today's conditions (normal, high wind, heavy rain or extreme heat) to see the matching safety alerts, then ask the built-in assistant any construction question.

> No API key? The app switches to a demo mode with sample results, so you can explore every screen.

## Built with

| Layer | Tools |
|---|---|
| Interface | Streamlit |
| AI | Google Gemini via `google-genai` |
| Images | Pillow |
| Concept renders | Pollinations AI |
| Data format | Structured JSON responses |

## How it works

```
Photo or form input
        ↓
Streamlit front end
        ↓
Task-specific prompt with a fixed JSON format
        ↓
Gemini analysis
        ↓
Parsed results → dashboard cards + JSON download
```

Nothing is stored. All data stays in the current browser session.

## Run it on your machine

1. Clone the repository
   ```bash
   git clone https://github.com/anureema30/Multimodal-construction.git
   cd Multimodal-construction
   ```
2. Create and activate a virtual environment
   ```bash
   python -m venv venv
   venv\Scripts\activate
   ```
3. Install the dependencies
   ```bash
   python -m pip install -r requirements.txt
   ```
4. Launch the app
   ```bash
   python -m streamlit run app.py
   ```
5. Open http://localhost:8501 in your browser

## Adding your Gemini key

Get a free key from [Google AI Studio](https://aistudio.google.com/apikey). You can either paste it into the sidebar, or save it in `.streamlit/secrets.toml`:

```toml
GOOGLE_API_KEY = "your-key"
```

That file is excluded from Git, so your key stays private.

## Publishing online

1. Upload the project to a public GitHub repository.
2. Sign in at [share.streamlit.io](https://share.streamlit.io) and choose **Create app**.
3. Select your repository, set `app.py` as the main file, and deploy.
4. Optionally add your key under **Advanced settings → Secrets**.

## Please note

Results come from an AI model and use simplified rate tables. They are meant for early screening and planning only, and they do not replace a certified safety audit, structural inspection or professional valuation.

## License

Released under the MIT License. See the [LICENSE](LICENSE) file.
