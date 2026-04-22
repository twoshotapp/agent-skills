# TwoShot Agent Skills

Agent skills for AI-powered audio-visual media creation with [TwoShot](https://twoshot.app).

Give your AI agent the ability to search and download media (samples, videos, images), generate music, create videos, clone voices, separate stems, build multi-track projects, and more.

## Install

```bash
npx skills add twoshotapp/agent-skills
```

Or install individual skills:

```bash
npx skills add twoshotapp/agent-skills/twoshot
npx skills add twoshotapp/agent-skills/twoshot-music-production
npx skills add twoshotapp/agent-skills/twoshot-video-creation
npx skills add twoshotapp/agent-skills/twoshot-voice-audio
```

## Skills

| Skill | Description |
|-------|-------------|
| **[twoshot](skills/twoshot/SKILL.md)** | Core setup and tools — MCP connection, API access, tool overview, credits |
| **[twoshot-music-production](skills/twoshot-music-production/SKILL.md)** | Music workflows — generation, sample search, stem separation, mashups, remixes, studio projects |
| **[twoshot-video-creation](skills/twoshot-video-creation/SKILL.md)** | Video workflows — animation, lyric videos, UGC talking-heads, visualizers, motion graphics |
| **[twoshot-voice-audio](skills/twoshot-voice-audio/SKILL.md)** | Voice workflows — podcasts, audiobooks, voice cloning, translation, TTS, vocal enhancement |

## Quick Start

1. Connect the TwoShot MCP server (`https://mcp.twoshot.app/`) to your agent:

   - **Claude Code:** `claude mcp add twoshot --transport http https://mcp.twoshot.app/`
   - **Claude Desktop:** Settings → Connectors → Add custom connector → paste the URL
   - **ChatGPT:** Settings → Connected apps → Add → paste the URL
   - **Codex CLI:** `codex mcp add twoshot --transport http https://mcp.twoshot.app/`
   - **Cursor:** add `{ "mcpServers": { "twoshot": { "url": "https://mcp.twoshot.app/" } } }` to `~/.cursor/mcp.json`
   - **VS Code (Copilot):** add `{ "servers": { "twoshot": { "url": "https://mcp.twoshot.app/" } } }` to `.vscode/mcp.json`
   - **Other clients:** connect to the URL via remote HTTP (Streamable HTTP protocol)

2. Authenticate when prompted (browser-based sign-in)

3. Ask your agent to create something:
   - "Find me some lo-fi drum loops around 85 BPM"
   - "Generate a chill synthwave track in A minor"
   - "Separate the vocals from this song and remix the instrumental as house"
   - "Create a lyric video for this track"
   - "Make a podcast episode about AI with two distinct speakers"
   - "Animate this album art into a looping video for Instagram"

## What TwoShot Can Do

- **Search** thousands of samples, videos, and images with BPM, key, tag, and style filters
- **Generate** music, sound effects, images, and video with AI models
- **Separate** stems (vocals, drums, bass, instruments) from any audio
- **Clone voices** and generate speech in any voice from a reference recording
- **Create podcasts** with multiple distinct AI speakers
- **Produce audiobooks** with voice cloning from a reference track
- **Translate** audio to other languages while preserving the original voice
- **Animate** still images into video with text-described or reference-based motion
- **Create lyric videos** with synced animated text over styled backgrounds
- **Generate UGC videos** — talking-head content from a reference video + new script
- **Build audio visualizers** — reactive visuals driven by frequency, amplitude, and beat data
- **Produce motion graphics** — HTML/CSS/JS rendered to video with audio reactivity
- **Mix and arrange** in a multi-track studio with clips, loops, and volume control
- **Import** from YouTube, Spotify, and any URL

## Links

- [TwoShot](https://twoshot.app)
- [MCP Server](https://mcp.twoshot.app)
- [API Docs](https://docs.twoshot.app)
