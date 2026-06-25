# 🎵 Canstein Musik

A Discord music bot supporting **YouTube, Spotify, Deezer, Tidal, SoundCloud, Apple Music** and many other platforms. Includes radio streaming, queue management, playlists, and autoplay.

## Features

- **Multi-Platform**: Music from YouTube, Spotify, Deezer, Tidal, Apple Music, SoundCloud, Bandcamp, Twitch & Vimeo
- **Radio**: 20+ predefined radio stations (DLF, BBC, BOB!, Jazz24, etc.) plus custom stream URLs
- **Queue**: Song queue with skip, loop (song/queue), shuffle & clear
- **Playlists**: Personal playlists (manual) & dynamic playlists (live-fetched from source)
- **Autoplay**: Automatically plays related songs for YouTube sources
- **Lyrics**: Song lyrics lookup
- **Slash Commands**: Fully controllable via Discord slash commands

## Prerequisites

- Python 3.10+
- [FFmpeg](https://ffmpeg.org/) (in system PATH or project directory)
- Discord Bot Token

## Installation

```bash
# Clone the repository
git clone https://github.com/ninocss/canstein-musik.git
cd canstein-musik

# Create virtual environment
python -m venv .venv
.venv\Scripts\activate  # Windows
# source .venv/bin/activate  # Linux/Mac

# Install dependencies
pip install -r requirements.txt
```

## Configuration

Copy `.env` and adjust the values:

```
DISCORD_TOKEN=your_bot_token
SERVER=your_guild_id
I_CHANNEL=channel_id_for_music_interface
MOD=admin
TRAIL_MOD=mod
```

## Running

```bash
python src/main.py
```

## Commands

| Command | Description |
|---------|-------------|
| `/play <song>` | Search or play a song URL |
| `/skip` | Skip current song |
| `/stop` | Stop playback & disconnect |
| `/pause` / `/resume` | Pause / Resume |
| `/queue` | Show the song queue |
| `/loop <off/song/queue>` | Set loop mode |
| `/shuffle` | Shuffle the queue |
| `/clear` | Clear the queue |
| `/volume <0-100>` | Change volume |
| `/lyrics` | Show lyrics |
| `/radio` | Start a radio stream |
| `/chart` | Play a random chart song |
| `/playlist` | Manage personal playlists |
| `/dynamic-playlist` | Manage dynamic playlists |
| `/nowplaying` | Show current song |

## Project Structure

```
src/
├── main.py              # Bot entry point
├── cogs/
│   ├── music.py         # Music player, queue, playlists
│   └── radio.py         # Radio streaming
├── util/
│   ├── constants.py     # Configuration & yt-dlp options
│   ├── music/queue.py   # Queue logic
│   ├── resolver/        # URL resolvers for Spotify, Deezer, Tidal, Apple Music
│   ├── playlist_db.py   # Database for personal playlists
│   ├── dynamic_playlist_db.py
│   ├── lyrics.py        # Lyrics lookup
│   └── cleaner.py       # Cleanup helpers
├── modals/embeds.py     # Embed definitions
├── views/               # Discord UI views (buttons, dropdowns)
└── lang/texts.py        # Text templates
```