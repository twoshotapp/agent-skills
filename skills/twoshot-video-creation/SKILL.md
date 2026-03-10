---
name: twoshot-video-creation
description: AI video and animation workflows with TwoShot — animate images, create lyric videos, UGC talking-head videos, audio-reactive visualizers, motion graphics, sprite sheets, and full video production. Use when the user wants to create, animate, or edit video content.
---

# Video Creation with TwoShot

Workflow patterns for video and animation using TwoShot's AI tools. All workflows use `twoshot_ask_assistant` — describe what you want in natural language.

## Animating Images

Turn still images into video:

- **Text-described motion**: provide image + motion description ("camera slowly pans right revealing the cityscape, wind blowing through trees, soft lens flare")
- **Motion transfer**: provide image + reference video showing desired movement — precise control for specific actions (dances, gestures, expressions)
- Describe what should move and how — "make just the water move but keep the sky still"
- Match output aspect ratio to source image for clean results
- Iterate: different motion style, extend the clip, loop it, add audio

## Lyric Videos

Full pipeline from audio to finished lyric video:

1. **Transcribe** — extract word-level timestamps from the audio
2. **Structure** — save transcript as sections (verse, chorus, bridge) for user review and editing
3. **Style** — clarify visual preferences: font, animations, colors, overall aesthetic
4. **Background** — create or find background assets:
   - AI-generated image animated into a subtle loop
   - Audio-reactive motion graphics scene
   - Existing video with looping treatment (generate smooth connection between start/end frames)
5. **Render lyrics** — motion graphics with transcript timestamps for smooth synced text
6. **Compile** — combine sections and add original audio track

Verify timing at each stage — lyrics must stay synced to the audio.

## UGC Talking-Head Videos

Create videos of a person speaking new content:

- **From reference video**: pass original video + new script text directly to the model — captures face, voice, accent, mannerisms, and setting
- **From photo only**: need a voice reference too — ask user to upload a recording or describe the desired voice
- Provide the EXACT script word-for-word — specific scripts produce clear, coherent speech
- Save script as a note for user review before generating
- Break longer scripts into scene-sized chunks within the model's duration limits
- Handle artifacts in source (subtitles, watermarks): describe the scene without artifacts in the prompt — models can generate clean output despite dirty references
- For recurring personas, build a persona element: face photos, voice recordings, mannerism clips — reusable across sessions

### Multi-Scene UGC
- Generate scenes in parallel where independent
- Each scene gets: video reference + exact script + scene description (body language, setting, expressions)
- Use each clip's native audio when stitching — only layer music/ambient underneath
- Add subtitles via motion graphics overlay for clean, styled, properly positioned text
- Transcribe the generated audio for accurate subtitle timestamps (actual speech may differ slightly from script)

## Audio Visualizers

Create visual companions for music tracks:

- **Simple background**: generate or find an image, animate into a subtle loop, combine with audio
- **Audio-reactive**: motion graphics driven by the audio's frequency spectrum, amplitude, and beat data
  - Frequency bars: perceptual spectrum for even bass-to-treble distribution
  - Pulsing/breathing effects: bass energy drives scale or glow intensity
  - Particle systems: amplitude modulates speed and density
  - 3D scenes: map frequency bands to geometry, color, or camera movement
- **Audiograms**: waveform or bar display with album art, artist name, progress indicator — sized for the target platform (square for Instagram, vertical for stories)
- Can combine AI-generated backgrounds with reactive overlays
- Motion graphics renders silent video — combine with original audio afterward
- Match visual energy to audio energy: bass-heavy tracks feel heavy, ambient tracks feel gentle

## Sprite Sheets & Game Animation

Generate animation frames for games:

- Generate sprite-style images with consistent character design
- Use frame transition techniques for smooth looping animation
- Extract individual frames for sprite sheets
- Create walk cycles, idle animations, attack sequences

## Video Reframing

Adapt video for different platforms:

- Extract a representative frame from the original video
- Extend the frame to the new aspect ratio (e.g., landscape to portrait)
- Use the extended image as a reference for AI video generation with the original motion
- Platform-specific sizing: 16:9 for YouTube, 9:16 for TikTok/Reels, 1:1 for Instagram

## Full Video / Movie Production

Large-scale multi-scene production:

1. **Brief** — develop visual tone, plot beats, character descriptions
2. **Screenplay** — save as structured script with scene breakdown and dialogue
3. **Character references** — generate first scene for each key character, establishing visual references
4. **Scene generation** — use established references for consistency, generate scenes in parallel
5. **Motion graphics** — intro credits, title cards, text overlays
6. **Sound design** — ambient atmosphere, foley, transition sounds, music
7. **Assembly** — stitch clips with transitions, layer audio underneath
8. **End credits** — motion graphics with credits and music

Build character/location elements as production assets for continuity across scenes and sessions.
