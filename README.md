# 🎧 Billboard to Spotify Playlist Generator (Python Automation)

A Python automation project that **scrapes the Billboard Hot 100 chart for a specific date and automatically creates a Spotify playlist with those songs**.

The program retrieves the list of songs from Billboard, searches for them on Spotify using the **Spotify Web API**, and adds them to a playlist in your Spotify account.

This project demonstrates **real-world API integration, web scraping, and automation using Python**.

## Image
<img width="977" height="609" alt="image" src="https://github.com/user-attachments/assets/f53ebaa5-ae56-40ec-9bd3-8d1912d611ae" />


## Features

- 📅 Fetch songs from the **Billboard Hot 100 chart for any date**
- 🌐 Scrape song titles from the Billboard website
- 🔎 Search each song on Spotify automatically
- 🎵 Create or update a Spotify playlist
- 📥 Add all found songs directly to the playlist
- ⚡ Uses Spotify OAuth authentication
- 🛡 Handles missing songs gracefully

---

## Technologies Used

- Python 3
- Requests (HTTP requests)
- BeautifulSoup (Web scraping)
- Spotipy (Spotify API wrapper)
- Spotify Web API
- OAuth Authentication

---

## Project Structure

```bash
billboard-spotify-playlist/
│
├── main.py           # Main automation script
├── token.txt         # OAuth token cache (auto-generated)
│
└── README.md
```
---

## Requirements

Ensure Python is installed:

python --version

### Install required libraries:

pip install requests
pip install beautifulsoup4
pip install spotipy

Or install everything at once:

pip install requests beautifulsoup4 spotipy
🔑 Spotify Developer Setup

Before running the project, create a Spotify Developer App.

Step 1 — Go to Spotify Developer Dashboard
https://developer.spotify.com/dashboard
Step 2 — Create a New App

Copy your:

Client ID
Client Secret
## Step 3 — Add Redirect URI

Add this redirect URI in your Spotify app settings:

https://developer.spotify.com/dashboard

## Step 4 — Add Credentials to the Script

YOUR_APP_CLIENT_ID = "your_client_id"
YOUR_APP_CLIENT_SECRET = "your_client_secret"
REDIRECT_URI = "https://developer.spotify.com/dashboard"

## How to Run the Project
Clone the Repository
git clone https://github.com/adebayoadesugba/billboard-spotify-playlist.git
Navigate into the Project Folder
cd billboard-spotify-playlist
Run the Script
python main.py


## 📊 How the Program Works
Step 1 — Scrape Billboard

The script sends a request to the Billboard Hot 100 chart page for a specific date.

Example:

https://www.billboard.com/charts/hot-100/2026-01-10

BeautifulSoup parses the page and extracts the song titles.

Step 2 — Search Songs on Spotify

Each song is searched on Spotify:

sp.search(q=f"track:{song}", type="track")

The program collects the Spotify URI for each track.

Step 3 — Add Songs to Playlist

All collected URIs are added to the playlist:

sp.playlist_add_items(playlist_id=playlist_id, items=song_uris)

🖥 Example Console Output

Logged in as: devbizzle

1. Title: Song Name
2. Title: Another Song
3. Title: Example Song

Total songs scraped from Billboard: 100

Searching Spotify for songs...

Found 94 songs! Adding them to your playlist...

Playlist complete! Go check your Spotify app again! 🎧
- 📚 Key Concepts Demonstrated
- Web scraping with BeautifulSoup
- API integration
- OAuth authentication
- JSON data parsing
- Automation with Python
- Exception handling
- Data extraction from websites


## ⚠️ Security Warning

Never upload your Client Secret to GitHub.

Use environment variables instead.

Example:

import os

CLIENT_ID = os.environ["SPOTIFY_CLIENT_ID"]
CLIENT_SECRET = os.environ["SPOTIFY_CLIENT_SECRET"]

## 🔮 Future Improvements
- Automatically create the playlist instead of manually pasting the playlist ID
- Include artist names for more accurate Spotify search
- Allow user input for chart date
- Export playlist data to CSV
- Add a GUI interface
-  automatic weekly playlist creation

## 👨‍💻 Author

Adebayo Adesugba

Full Stack Developer
Python | JavaScript | React | Node.js | AI Development

##⭐ Support

If you like this project:

⭐ Star the repository
🍴 Fork it
🧑‍💻 Contribute
📜 License

This project is open-source and available under the MIT License.
