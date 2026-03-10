---
name: twoshot
description: Connect your AI agent to TwoShot for audio-visual media creation — search audio samples, generate music/video/images, separate stems, clone voices, build multi-track projects, and more. Use when the user needs audio, music, video, image creation or manipulation.
---

# TwoShot

TwoShot is an AI-powered platform for audio-visual media creation. It provides search, generation, analysis, and editing tools for audio, music, video, and images — all accessible through natural language.

## Setup via MCP (Recommended)

The MCP server gives your agent direct tool access. One-time setup:

**Claude Code:**
```
claude mcp add twoshot --transport streamable-http https://mcp.twoshot.app/
```

**ChatGPT:** Settings > Connected apps > Add > enter `https://mcp.twoshot.app/`

**Other MCP clients:** Connect to `https://mcp.twoshot.app/` using Streamable HTTP transport. Authentication is OAuth 2.0 + PKCE (browser-based sign-in on first use).

## Setup via API (Alternative)

For agents without MCP support, use the REST API directly:
- API docs: https://docs.twoshot.app
- Base URL: `https://api.twoshot.app`
- Auth: Bearer token (API key from account settings)

## Available MCP Tools

### Search & Browse
- **twoshot_search_samples** — Search audio samples by keyword, tags, BPM range, musical key/scale. Combine filters for precise results (e.g. "lo-fi drums" + 80-90 BPM + "C minor").
- **twoshot_search_videos** — Search videos by keyword, duration, AI-generated filter.
- **twoshot_search_images** — Search images by keyword, aspect ratio, AI-generated filter.
- **twoshot_browse_library** — Browse the user's personal library and folders.

### Content Details
- **twoshot_get_content** — Get full metadata for a specific sample, video, or image (name, creator, duration, tags, etc.).
- **twoshot_get_download_url** — Get a signed download URL. Sample downloads cost credits (scaled by duration). Video and image downloads are free. Only call when the user explicitly wants to download.

### Import
- **twoshot_import_media** — Import content from external URLs (YouTube, Spotify, direct links, etc.) into the user's library. Specify `type: "audio"` for audio-optimized import, `type: "image"` for images, or omit for auto-detection.

### AI Assistant (the power tool)
- **twoshot_ask_assistant** — Send a natural-language request to TwoShot's AI production assistant. This is the most powerful tool — it delegates to 90+ internal capabilities including music generation, stem separation, voice cloning, video creation, motion graphics, multi-track studio projects, and complex multi-step workflows.

Use `twoshot_ask_assistant` for any creative task beyond simple search/browse. Describe what you want in plain language.

Examples of what the assistant handles:
- "Generate a lo-fi hip hop beat at 85 BPM in C minor"
- "Separate the vocals from this track and remix the instrumental as dark techno"
- "Create a lyric video for this song with animated text synced to the vocals"
- "Make a podcast with two speakers discussing AI trends"
- "Animate this album art into a looping video for Instagram"
- "Clone my voice from this recording and narrate this script"
- "Create a UGC-style talking head video with this script"
- "Build a multi-track project: drums, bass, melody, and vocals"

Pass `session_id` from a previous response to continue a multi-turn conversation with the assistant.

## Resources

- **twoshot://profile** — Current user's profile (name, tier, verification status).
- **twoshot://credits** — Credit balance and usage. Check before expensive operations.

## Credits

TwoShot uses a credit system:
- Audio sample downloads cost credits (scaled by duration)
- AI generation (music, video, images, voice) costs credits
- Video and image downloads are free
- Check `twoshot://credits` to see available balance

## Workflow Tips

- For simple lookups (find a sample, check metadata), use the individual search/browse tools directly — faster and cheaper.
- For anything creative or multi-step, use `twoshot_ask_assistant` — it handles complex workflows like stem separation cascades, multi-speaker podcasts, lyric video pipelines, and full movie production.
- The assistant maintains session state, so you can iterate: "make it faster", "try a different style", "add more bass".
- Import external content first with `twoshot_import_media`, then reference it in assistant requests.
