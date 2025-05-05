# Discord Audio Bridge

A WebRTC to Discord audio bridge that allows you to stream audio from a web interface directly to a Discord voice channel.

## Description

This application creates a bridge between WebRTC audio streams and Discord voice channels. It enables:

- Real-time audio forwarding from a web browser to Discord
- Seamless Opus audio codec compatibility
- Simple web interface for establishing connections

## Features

- WebRTC audio capture from browser
- Discord voice channel integration
- Automatic Opus codec handling
- Web-based control interface

## Requirements

- Go 1.16+
- Discord Bot with proper permissions
- STUN server access (defaults to Google's public STUN server)

## Environment Variables

Create a `.env` file in the project root with the following variables:

```
DISCORD_BOT_TOKEN=your_discord_bot_token
DISCORD_GUILD_ID=your_discord_server_id
DISCORD_CHANNEL_ID=your_voice_channel_id
YOUTUBE_API_KEY=your_youtube_api_key (optional)
```

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/discord-audio-bridge.git
   cd discord-audio-bridge
   ```

2. Install dependencies:

   ```bash
   go mod download
   ```

3. Build the application:
   ```bash
   go build
   ```

## Usage

1. Start the server:

   ```bash
   ./discord-audio-bridge
   ```

2. Open your web browser and navigate to:

   ```
   http://localhost:8080
   ```

3. Grant microphone permissions in your browser and begin streaming audio to Discord

## Development

The server runs on port 8080 by default and provides:

- Static file serving from the `./static` directory
- WebRTC signaling via WebSocket at `/rtc`
- YouTube API key endpoint at `/api/youtube-key` (if configured)

## License

[Add your license information here]

## Acknowledgements

- [discordgo](https://github.com/bwmarrin/discordgo) - Discord API wrapper
- [Pion WebRTC](https://github.com/pion/webrtc) - WebRTC implementation
- [Gorilla WebSocket](https://github.com/gorilla/websocket) - WebSocket implementation
