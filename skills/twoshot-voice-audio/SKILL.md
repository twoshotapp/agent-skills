---
name: twoshot-voice-audio
description: AI voice and speech workflows with TwoShot — create podcasts with multiple speakers, produce audiobooks with voice cloning, translate audio while preserving the original voice, convert voices, text-to-speech, and vocal enhancement. Use when the user wants to create spoken content, clone voices, or process vocals.
---

# Voice & Audio Production with TwoShot

Workflow patterns for voice, speech, and spoken-word production using TwoShot's AI tools. All workflows use `twoshot_ask_assistant` — describe what you want in natural language.

## Podcast Creation

Create podcasts with distinct speakers and professional production:

1. **Format** — clarify: solo narration, two-person interview, multi-host roundtable, fiction/drama
2. **Script** — research topic if needed (web search), write distinct perspectives for each speaker with natural back-and-forth reactions (not just Q&A), break into segments (intro, topics, transitions, outro), save as a note for user review
3. **Voice setup** — each speaker needs a distinct voice (pitch, pace, tone, accent):
   - User can upload voice references, describe desired voices, or use default TTS voices
   - Generate the first actual line of dialogue for each speaker as the preview — this IS the quality sample and real content
   - If a voice sounds wrong, regenerate that line with adjusted settings — the approved take becomes the reference for remaining lines
   - For recurring podcasts, save approved voice samples into a persona element for consistent casting across episodes
4. **Generate** — remaining speech segments in parallel (each speaker's lines are independent, batch in a single turn)
5. **Post-production** in a studio project:
   - Layer intro/outro music underneath speech (keep music well below voice level)
   - Add transition sounds or music beds between segments
   - Normalize volume across speakers
6. **Verify** each speaker sounds distinct and conversation flows naturally

## Audiobook Production

Create audiobooks with voice cloning from a reference:

1. **Text** — save as script organized by chapters/sections, or fetch attached script
2. **Voice reference** — extract vocals from user's track using stem separation, or use an uploaded voice recording
3. **Generate** — voice cloning TTS with extracted vocals as reference + script text
   - Generate first chapter first — this IS the voice quality preview and real content
   - If the voice sounds off, regenerate with adjusted settings before continuing
4. **Ambient layer** — combine narration with background audio (ambient sounds, gentle music) in a studio project
5. **Fallback** — if voice extraction fails or no vocals found, offer standard narrator voice

## Translation with Voice Preservation

Translate spoken content while keeping the original speaker's voice:

1. **Transcribe** — extract text from the original audio
2. **Translate** — convert transcript to target language, save as note for user review/editing
3. **Voice clone** — original audio as voice reference + translated text generates speech in the original voice but in the new language
4. **Verify** — cloned voice matches original in accent, pitch, and pacing
5. **Fallback** — if voice cloning isn't available, standard TTS preserves the content but not the voice

## Voice Conversion

Change the speaker's identity while preserving the content:

- **With a trained voice model**: apply directly to the user's audio
- **With a reference recording**: voice swap model uses reference + input audio
- **From a description**: design the voice first (create a synthetic voice sample), then use as reference for voice swap

Preparing voice references:
- Search library for clean voice samples, or import from YouTube (interviews for speech, isolated vocals for singing)
- Requirements: clean solo voice, no background music/noise, 10-30 seconds of audio
- If reference has background music, separate vocals first
- If audio has instrumental, separate stems first, convert vocal only, merge back in a studio project — voice conversion works best on isolated vocals

For recurring voice personas, collect reference samples into an element: clean takes, different pitches/emotions, speaking and singing if both needed.

## Vocal Enhancement

Clean up and enhance vocal recordings:

1. **Separate** — extract vocals from the mix (stem separation)
2. **Dereverb** — remove room reverb/echo for a dry signal
3. **Enhance** — apply quality enhancement/upscaling for clarity
4. Each step cascades — progressively cleaner results
5. If the target vocal is already dominant, offer cleanup/enhancement directly instead of separation

## Text-to-Speech

Generate speech from text:

- Multiple voice models with different characteristics (pitch, pace, tone, accent)
- Style control through prompt description
- Save scripts as notes for review before generating
- Generate first line as preview, iterate on voice before producing full content
- For long-form content, break into segments and generate in parallel
