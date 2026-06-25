# STT and audio processing rules

## Backend (Go)
- Do not use full-file loading (`os.ReadFile`) to process large audio files. Always stream via `io.Reader` or `io.Copy`.
- If you call an external STT API (e.g. OpenAI Whisper), always set `context.WithTimeout` to at least 60 seconds, as audio processing takes a while.

## Frontend (React)
- When recording from a microphone via `MediaRecorder`, strictly check the supported audio formats (prefer `audio/webm` or `audio/mp4` depending on the browser).
- Always properly cleanup audio streams in `useEffect` to avoid a locked microphone hanging on Windows.