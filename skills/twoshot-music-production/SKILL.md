---
name: twoshot-music-production
description: AI-powered music production workflows with TwoShot — generate music, find and filter audio samples, separate stems, create mashups and remixes, enhance vocals, and build multi-track studio projects. Use when the user wants to create, edit, or produce music or audio.
---

# Music Production with TwoShot

Workflow patterns for music and audio production using TwoShot's AI tools. These workflows use `twoshot_ask_assistant` for generation and processing, and the search/browse tools for finding existing content.

## Finding Samples

Use `twoshot_search_samples` with combined filters for precise results:

- **BPM + genre**: "trap hi-hats" with bpm_min=140, bpm_max=150
- **Key + style**: "melodic piano" with scale="C minor"
- **Tags**: Filter by specific tags like `["lofi", "drums"]`

Search tips:
- Subgenre terms (boom bap, kpop) may not match well — use descriptive phrases alongside them ("gritty muffled drums boom bap")
- "Fast" is relative to genre: trap fast = 140+ BPM, DnB fast = 170+
- Broad terms like "melodic" need expanded descriptions ("melodic loops musical phrases catchy melodies instrumental")
- Try `sort: "random"` for exploration, `sort: "popular"` for proven quality
- If results are limited, broaden search terms or try related styles before giving up
- Offer to generate custom content if nothing in the library matches

## Generating Music

Ask the assistant to generate audio with a detailed style description:

- Paint the sonic picture: "dark techno with industrial grit, driving four-on-the-floor kicks, brooding pads, hypnotic bass" rather than just "make techno"
- Specify tempo, key, mood, instrumentation, and energy level when relevant
- Reference audio works well — import a track and ask "generate something in this style"
- Different generation models have different sonic characteristics — if results don't match, ask the assistant to try a different model
- Iterate: "make it darker", "add more swing", "try at 120 BPM instead"

## Stem Separation

Ask the assistant to separate/split audio. Multi-step cascade for cleanest results:

1. **Initial split** — separate into vocals, drums, bass, other
2. **Deeper extraction** — split individual stems further:
   - Vocals stem → individual voice separation (if multiple singers)
   - Drums stem → kick, snare, hi-hats breakdown
   - "Other" stem → text-prompted extraction for specific instruments ("piano", "guitar", "synth pad")
3. **Cleanup** — apply dereverb and enhancement to isolated stems for cleaner results

Text-prompted extraction is powerful for sounds without a dedicated splitter — describe the target sound and the model extracts it from the mix.

## Mashups

Ask the assistant to create a mashup from two tracks:

1. **Analysis** — the assistant checks genre, tempo, and key compatibility
2. **AI mashup** — primary approach: feed both tracks to a mashup model with a combined style description
3. **Manual fallback** — if AI mashup doesn't blend well: separate stems from both tracks, combine vocals from one with instrumental from the other in a studio project, adjusting tempo/key as needed
4. **Iteration** — different blend balance, swap which elements come from which track, try a different style

## Remixing

Ask the assistant to remix a track in a new style:

- **Full remix** — reinterprets everything (vocals + instrumental) in the new genre
- **Keep original vocals** — separates stems first, generates new instrumental around the existing vocals
- Style description matters: detailed sonic painting produces better results
- Manual fallback: separate stems, generate new elements, combine in studio

## Vocal Enhancement

Ask the assistant to clean up or enhance vocals:

1. **Separate** — extract vocals from the mix
2. **Dereverb** — remove room reverb/echo for a dry signal
3. **Enhance** — apply quality enhancement/upscaling
4. Each step builds on the previous — cascade produces progressively cleaner results

## Studio Projects

Ask the assistant to build a multi-track project for complex arrangements:

- Create projects with specific tempo and structure
- Place audio clips on multiple tracks at precise positions
- Loop clips to extend them across the timeline
- Layer elements: drums, bass, melody, vocals, effects
- Adjust volume levels between tracks
- Render the final mix to audio when ready

Useful for:
- Podcast post-production (speech + music + transitions)
- Mashups requiring manual arrangement
- Layering generated elements with existing samples
- Building full songs from individual stems and generated parts
