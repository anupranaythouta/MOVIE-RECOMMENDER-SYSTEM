
# Movie Recommender System (TMDb dataset)

A small content-based movie recommender built with Streamlit. The app uses precomputed similarity data (pickles) derived from the TMDb dataset and fetches movie posters from The Movie Database (TMDb) API.

Demo GIF: a short demo of the application is included below.

![App demo](Assets/vid_movie_recommender.gif)

## Repository layout (recommended)
The project uses a clear separation of concerns:

- `Code/` — application source code and notebooks. Run the app from here (see below).

- `Data/` — raw CSVs and original datasets (e.g. `tmdb_5000_movies.csv`, `tmdb_5000_credits.csv`).

This keeps code, raw data and generated model artifacts separate and easier to manage.

## What this repository contains
- `Code/app.py` — Streamlit application. Select a movie and click "Show Recommendation" to see similar titles and posters.
- `Data/` — raw CSV files used to build the pickles.
- Note: precomputed pickle files are NOT committed. Generate them by running the notebook in `Code/` (see below) which will create a local `Models/` folder containing `movie_list.pkl` and `similarity.pkl`.
- `Code/movie_recommender.ipynb` — notebook used during exploration / data preparation.

## Requirements

- Python 3.8+ (tested on 3.8–3.11)
- Packages: `streamlit`, `pandas`, `requests`

Install with pip:

```powershell
python -m pip install --user streamlit pandas requests
```

Or in a virtual environment:

```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1; pip install streamlit pandas requests
```

## Running the app (Windows / PowerShell)

1. Open PowerShell and change to the repository root:

```powershell
cd "PathToRepositoryRoot"
```

2. Start the Streamlit app pointing at the script in `Code/`:

```powershell
streamlit run .\Code\app.py
```

3. By default Streamlit shows the app at `http://localhost:8501`.

- Open it in your default browser:

```powershell
start "http://localhost:8501"
```

- To open specifically in Google Chrome:

```powershell
Start-Process "C:\Program Files\Google\Chrome\Application\chrome.exe" -ArgumentList "http://localhost:8501"
```

If the app doesn't appear, try running on a different port:

```powershell
streamlit run .\Code\app.py --server.port 8502
start "http://localhost:8502"
```
