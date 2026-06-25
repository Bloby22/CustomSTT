# CLAUDE.md – STT (Speech-to-Text) Project

This file defines the rules and context for AI agents working in this repository.

The project is an STT (Speech-to-Text) application built on a React + Vite frontend and a Go backend with a local Whisper GGML model.

---

## 🧠 Project Architecture

### Frontend
- Framework: React + Vite
- Responsibility:
- UI for audio recording
- display of the ongoing / final transcript
- communication with the backend (API / streaming)

### Backend
- Language: Go
- Responsibility:
- processing of audio inputs
- STT inference using Whisper Small GGML
- providing API for the frontend
- orchestration of transcription

### STT engine
- Whisper Small GGML (local run)
- Use for offline / low-latency transcription
- Backend calls the model locally

---

## 🔌 Communication

- Frontend ↔ Backend:
- API (HTTP)
- optionally streaming (if implemented)
- Backend returns text transcript of audio

---

## 🚀 Project launch

### Frontend (React + Vite)
```bash
npm install
npm run dev