# AI Learning App

An on‑premises, API-First learning assistant that:

- **Organizes** your entire curriculum into bite‑sized daily lessons  
- **Generates** strict, no‑hint quizzes to test mastery  
- **Auto-creates** spaced‑repetition flashcards to lock in memory  
- **Transcribes** your voice inputs (Whisper) so you can speak questions and notes  
- **Scans** your handwritten pages (OCR) to ingest formulas, diagrams, and freehand notes  
- **Observes** your study habits and performance, then **adapts** each lesson’s difficulty and pacing  
- **Enables** group study via a Multi‑User Dashboard  
- **Optimizes** in real time—anticipating struggles and injecting mini‑lessons on the fly  
- **Secures** every call through a local proxy that pseudonymizes and minimizes all data

---

## What Each Proxy/API Endpoint “Builds”

| Endpoint                                | Role in AI Core                                   |
|-----------------------------------------|---------------------------------------------------|
| **POST /proxy/openai/schedule**         | “Builds” your daily and weekly lesson plan from your curriculum JSON; maps tasks to calendar slots. |
| **POST /proxy/openai/quiz**             | Creates a set of assessment questions (no hints) that probe your understanding of current topics. |
| **POST /proxy/openai/flashcards**       | Transforms lesson content and quiz Q&A into spaced‑rep flashcards, scheduling optimal review intervals. |
| **POST /proxy/whisper/transcribe**      | Converts 1–2 min voice inputs into text prompts—used for immediate note‑taking and Q&A. |
| **POST /proxy/ocr/handwriting**         | Parses uploaded handwritten pages, extracting text and math so they feed into the observation engine. |
| **(Future) POST /proxy/vision/engagement** | Analyzes webcam frames to detect facial cues (confusion, engagement) and adapt lesson flow in real time. |

Each call includes a **`SYSTEM_CONTEXT`** message so the LLM “knows” all nine core modules and returns responses tailored to your learning workflow.

---

## Full Feature List & Learning Flow

1. **Lesson Structuring & Scheduling** (Day 1)  
   - Input: Curriculum JSON (subjects, assignments, due‑dates)  
   - Output: Per‑day study plan, calendar events  

2. **Custom Subject Focus** (Day 1)  
   - Toggle between “Strict Curriculum” vs. “Deep Dive” modes on any topic  

3. **Test & Quiz Generation** (Day 4)  
   - Input: Lesson content  
   - Output: Quiz with no‑hint questions to enforce active recall  

4. **AI‑Driven Flashcards** (Day 5)  
   - Input: Quiz Q&A or lesson summaries  
   - Output: Spaced‑rep flashcard decks with review schedule  

5. **Voice Interaction & Dictation** (Day 8)  
   - Speak aloud questions or notes; receive instant transcription  

6. **Handwriting Recognition (OCR)** (Day 10)  
   - Upload sketches, formulas, handwritten notes; get parsed text  

7. **Homework Observation & Analytics** (Day 10)  
   - Passive tracking of your note‑taking, quiz results, flashcard reviews; feeds the adaptive engine  

8. **Strict Testing System** (Day 12)  
   - After mastery thresholds, quizzes auto‑upgrade in difficulty  

9. **Adaptive Learning Personalization** (Day 15)  
   - Dynamically adjusts upcoming lessons’ difficulty/pacing based on performance metrics  

10. **Multi‑User Dashboard** (Day 22)  
    - Invite peers, compare progress, run group quizzes and reviews  

11. **Advanced Real‑Time Optimization** (Day 25)  
    - Predicts struggles mid‑session and injects micro‑lessons or examples  

12. **(Optional) Engagement Monitoring** (Post‑Day 21)  
    - Facial‑expression sensing to detect confusion/engagement and adapt on the fly  

13. **Full Cut‑Over to On‑Prem AI** (Day 28)  
    - Flip all API keys off—your Dockerized LLM, Whisper, OCR, and engagement services run entirely in your environment.

---

## Quick Start

1. **Clone & Codespace:**  
   ```bash
   git clone git@github.com:<you>/ai-learning-app.git
   cd ai-learning-app
