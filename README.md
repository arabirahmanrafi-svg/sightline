# SightLine 👁️🔊
**AI eyes that talk: point your phone and hear the world.**

Built at **Hack The Nest 2026** (Eastern Michigan University) by Team **The Hatchlings**.

🔗 **Live app:** https://slim-sight-line-vision.base44.app

## What it does
SightLine is a voice-first web app for blind and low-vision people. Tap anywhere on the camera view and it speaks what it sees.

| Mode | What it does |
|---|---|
| Scene | Describes surroundings, safety issues first, with left/right/ahead directions |
| Read | Reads text, summarizes letters and bills, tells you what to do and by when |
| Find | Tells you whether an object is visible and where |
| Money | Identifies bills and coins |
| Color | Identifies colors, helps sort laundry and match clothes, checks whether food looks fresh |
| Medicine | Reads labels, warns about expired items, answers questions with cited web sources |
| Guide | Real-time obstacle alerts while walking (on-device AI) |

**Plus:** voice follow-up questions · Pocket mode (shake to describe, hands-free) · SOS with GPS location · 30+ languages with auto-detection · audio cues

## Tech stack
- **Base44**: app, backend functions, secrets, database, hosting
- **ElevenLabs**: Text to Speech (Flash v2.5, Multilingual v2), Speech to Text (Scribe), Sound Effects
- **Google Gemini 3.5 Flash**: vision for every camera mode
- **Exa Answer API**: trusted web lookups with sources
- **TensorFlow.js COCO-SSD**: on-device obstacle detection

## How it works
1. The camera frame is resized on the phone and sent to a backend function that calls Gemini with a mode-specific prompt.
2. The answer is spoken through ElevenLabs text-to-speech, in the user's language.
3. Follow-up questions are recorded, transcribed with ElevenLabs Scribe, and asked about the same photo.
4. Guide mode runs COCO-SSD in the browser for instant obstacle alerts, with a cloud check every 8 seconds for stairs and doors.
5. Medicine questions are answered with Exa's Answer API, and the source is read aloud and shown on screen.

## Accessibility
Every control has a screen-reader label (VoiceOver / TalkBack), all answers are spoken automatically, touch targets are large, the whole camera view is a tap target, and Pocket mode works without looking at the screen.

## What's next
- Talk mode: real-time hands-free conversation with ElevenLabs Agents
- Personal memory ("remember my blue mug")
- Testing with blind and low-vision users, and an App Store release

## Team
Arabi Rahman Rafi · Kazi Tanisha Tamannum · Faizah Fatima (Eastern Michigan University) · Vanshi Patel (St Ann's High School)
