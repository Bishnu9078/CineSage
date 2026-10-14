# CineSage

CineSage is a Streamlit app that extracts structured movie information from a
plain-language paragraph. It uses LangChain with a Groq-hosted chat model and a
Pydantic parser to return clean movie details that can be viewed in the browser
or downloaded as JSON/TXT.

## Features

- Extracts movie title, release year, genre, director, cast, rating, and summary.
- Uses a strict Pydantic schema for structured output.
- Shows results in a readable Streamlit interface.
- Includes a raw JSON preview for developers.
- Exports extracted movie information as `.json` and `.txt` files.
- Keeps API keys outside the code through `.env` configuration.

## Project Structure

```text
.
|-- UIcore.py          # Streamlit app interface
|-- core.py            # LangChain prompt, model setup, and movie schema
|-- .env.example       # Example environment variable file
|-- .gitignore
|-- README.md
`-- requirements.txt
```

## Requirements

- Python 3.13 or newer
- Groq API key

## Setup

1. Clone the repository:

```bash
git clone https://github.com/Bishnu9078/CineSage.git
cd CineSage
```

2. Create and activate a virtual environment:

```bash
python -m venv .venv
.venv\Scripts\activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Create a `.env` file from the example:

```bash
copy .env.example .env
```

5. Add your Groq API key inside `.env`:

```env
GROQ_API_KEY=your_groq_api_key_here
```

## How To Run

Start the Streamlit app:

```bash
streamlit run UIcore.py
```

Paste or type a movie paragraph, then click **Extract Data**. CineSage will
show the extracted movie details and provide download buttons for JSON and TXT
exports.

## Notes

- Do not commit the real `.env` file because it contains private API keys.
- Downloaded JSON/TXT movie exports are local output files and do not need to be committed.
- The app currently uses the Groq-hosted `openai/gpt-oss-20b` model configured in `core.py`.
