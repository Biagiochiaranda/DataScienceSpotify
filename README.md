# Spotify Data Science — Playlist Network Analysis

**Exploring Spotify playlists and music categories through data collection, network analysis, and visualization.**

This data science project investigates relationships between Spotify playlists. By examining playlist categories and tracks shared across playlists, it represents the music ecosystem as a graph and explores how playlists connect to one another.

## Project Goals

- Retrieve and explore music categories and playlists using the Spotify Web API.
- Collect playlist and track information for further analysis.
- Identify shared tracks between playlists.
- Model playlists as graph nodes and shared-track relationships as edges.
- Analyze and visualize the resulting network using Python tools.

## Methodology

### 1. Data Gathering

The notebook `1 Spotify Data Gathering.ipynb` uses **Spotipy** and the Spotify Web API to retrieve categories, category playlists, and related data. It explores the Italian Spotify catalog (`country='IT'`, `locale='it_IT'`).

### 2. Data Preparation

The analysis parses playlist-to-category and playlist-to-track associations, removes duplicate track identifiers within playlists, and constructs mappings between playlists and their categories.

### 3. Graph Construction

Each **node** represents a playlist. An **edge** connects two playlists that share at least one track. Edge weights express the strength of the relationship through their shared tracks. The analysis explores both undirected and directed graph representations in NetworkX.

### 4. Network Exploration

`2 Spotify Analysis.ipynb` builds graph structures and examines their sizes and connectivity. The included `.gexf` file provides a portable graph representation for compatible network-visualization software, such as Gephi.

## Technologies

| Tool | Role |
| --- | --- |
| Python / Jupyter Notebook | Data exploration and analysis |
| Spotipy | Spotify Web API access |
| Pandas / NumPy | Data preparation and processing |
| NetworkX | Playlist network modeling |
| GEXF / Gephi-compatible format | Graph exchange and visualization |

## Repository Contents

```text
DataScienceSpotify-main/
├── 1 Spotify Data Gathering.ipynb  # API data collection
├── 2 Spotify Analysis.ipynb        # Playlist network analysis
├── Prove.ipynb                     # Experiments and exploratory tests
├── categorie.csv                   # Collected category data
├── toplists_songs_id.csv           # Track identifiers
└── grafo_completo.gexf            # Exported graph
```

## Reproducing the Analysis

1. Create a Python environment with Jupyter, Spotipy, Pandas, NumPy, and NetworkX.
2. Obtain your own Spotify developer credentials and configure them securely via environment variables or a local, untracked configuration file.
3. Review `1 Spotify Data Gathering.ipynb` to understand collection and any API compatibility changes.
4. Review `2 Spotify Analysis.ipynb` to explore graph creation and analysis.
5. Import `grafo_completo.gexf` into Gephi or another GEXF-compatible tool to inspect the network.

**Important:** `2 Spotify Analysis.ipynb` references additional CSV files (including `categorie-playlists.csv` and `playlists-tracks.csv`) that were not included in the supplied archive. Therefore, the notebooks are not guaranteed to run end-to-end without recreating these intermediate datasets and updating the original workflow for current API behavior.

## Security and Data Usage

**Before publishing this repository, remove and revoke the Spotify API client secret embedded in the notebooks.** Replace hard-coded credentials with environment-based configuration, and check notebook outputs and Git history as well. A README alone does not fix exposed credentials.

Spotify data and API access are subject to Spotify's developer terms and applicable restrictions. Attribute original data sources and do not redistribute data beyond permitted uses.

## Author

**Biagio Chiarandà**

## License

No software license was supplied. Specify a license for your own original analysis separately from any third-party data or API content.
