# Research Paper Project Idea Generator

A simple web application that helps you generate project ideas based on research-paper content. Powered by a FastAPI Python backend and a single-page browser UI.

---

## Features

- **Search** for project ideas based on research keywords.
- **Generates unique ideas** from recent research papers.
- Browse **5 suggestions per page** with next/previous navigation.
- **Save ideas** in-browser for later review (no sign-up required).
- Responsive, minimal interface using plain HTML, CSS, and JS.
- No database required – simply launch and use.

## Tech Stack

| Part      | Tech/Details    | Where/How                 |
|-----------|----------------|---------------------------|
| Backend   | Python, FastAPI | `main.py`, `idea_generator.py` |
| Frontend  | HTML/CSS/JS     | `templates/index.html`, `static/script.js`, `static/style.css` |
| Runtime   | Uvicorn         | Run FastAPI server        |
| External  | Research paper API | Fetched by backend        |

---

## Project Structure

```
project-root/
├── main.py                # FastAPI entry point & routes
├── idea_generator.py      # Generates ideas from research papers
├── templates/
│   └── index.html         # Main browser page
├── static/
│   ├── script.js          # Handles client-side logic (AJAX, UI)
│   └── style.css          # Styles for the UI
└── README.md
```

---

## How It Works

1. **User searches**: Enter a keyword in the UI and hit search.
2. **Frontend JS** uses AJAX to call the FastAPI `/search` endpoint.
3. **Backend** (`main.py`) processes the request:
    - Coordinates request/response.
    - Calls `idea_generator.py` to fetch research papers and produce project ideas.
4. Returns titles, abstracts, and generated ideas to the frontend.
5. **Frontend** renders results & allows pagination (5 per page).
6. **Users can save ideas** (local browser state, no backend storage).

---

## Setup & Running

### Prerequisites

- Python 3.8+
- pip

### Installation

1. **Clone this repo:**
   ```sh
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   cd YOUR_REPO_NAME
   ```

2. **Install dependencies:**
   ```sh
   pip install fastapi uvicorn httpx jinja2
   # include others as required by idea_generator.py
   ```

3. **Run the server:**
   ```sh
   uvicorn main:app --reload
   ```

4. **Access the app:**
   Open your browser at [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## API Endpoints

- `GET /` : Loads main page (`index.html`)
- `POST /search` : Receives keyword, returns titles/abstracts/ideas (JSON)
    - Expected payload: `{ "keyword": "deep learning" }`
    - Returns: `{ "ideas": [ ... ] }`

_The backend may also proxy/fetch data from an external research paper API. API setup/keys should be configured in `main.py` or as environment variables as needed._

---

## Customizing & Extending

- **Idea Generation**: Edit `idea_generator.py` to change how ideas are formed.
- **UI/UX**: Tweak `static/style.css` and `templates/index.html`.
- **Search logic**: Modify backend (e.g., use a different API, add filters).

---

## Limitations & Notes

- No authentication or user accounts.
- Saved ideas are NOT stored on the server (browser only).
- Dependent on availability of external research paper data/API.

---

## Contributers Name
- **Amruta Katkar**
- **Rutuja Patil**
- **Mruganayani tate**
- **AAkanksha Bugad**
