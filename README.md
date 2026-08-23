# Code w/ Claude — San Francisco 2026 · Full Transcripts

Anthropic uploaded the complete session recordings from their **Code w/ Claude** event in San Francisco — ~8 hours across **19 videos**, free on YouTube. This folder holds a clean, readable transcript of **all 19** talks, each with an AI-generated thesis + key-points summary at the top.

Talks span keynotes, workshops, and demos, featuring Dario & Daniela Amodei, Boris Cherny (creator of Claude Code), Guillermo Rauch (Vercel), Jarred Sumner (Bun), and teams from Cognition, Gamma, Harvey, Datadog, Asana, Google Cloud, Replit, and Cursor.

## How these were made

Each transcript was produced from the YouTube audio with:

- **[Deepgram Nova-3](https://deepgram.com/)** — pre-recorded transcription with smart formatting, punctuation, and paragraphing, automatic language detection, no chunking (handles long audio natively). Blazing fast — the opening keynote's 47 minutes transcribed in ~5 seconds (530× realtime).
- **Gemini Flash-Lite** — generates the `## Thesis` + `## Key Points` summary block at the top of each file.

Every `.txt` file is structured as:

```
Transcript: <title>          ← header: language, paragraph count, RTFx, processing time
────────────────────────────
## Thesis / ## Key Points     ← AI summary
════════════════════════════
TRANSCRIPT                    ← full readable transcript, paragraph-formatted
```

## The 19 sessions

Session titles link to the YouTube video. Files are numbered by session order. All transcribed successfully; all detected as English.

| # | Session (▶ click to watch) | Duration |
|---|----------------------------|----------|
| 1 | [Opening Keynote](https://www.youtube.com/live/GMIWm5y90xA) | 47:29 |
| 2 | [A conversation with Dario & Daniela Amodei](https://www.youtube.com/live/7xco5Qd2Oo8) | 33:10 |
| 3 | [What's new in Claude Code](https://www.youtube.com/live/IMZa42k6L6M) | 24:55 |
| 4 | [Live coding session with Boris Cherny & Jarred Sumner](https://www.youtube.com/live/DlTCu_pNDHE) | 32:00 |
| 5 | [Caching, harnesses, and advisors: Building on Claude at GitHub scale](https://www.youtube.com/live/y5TmF_6o6xk) | 26:15 |
| 6 | [Getting to production faster with Claude Managed Agents](https://www.youtube.com/live/E9gaQHrw_rg) | 17:25 |
| 7 | [Building AI-native: Inside the stacks powering Cognition, Gamma, and Harvey](https://www.youtube.com/live/OFDm3T7pVlc) | 28:15 |
| 8 | [Getting more out of the Claude Platform](https://www.youtube.com/live/7oO37GRhwGk) | 28:15 |
| 9 | [How Datadog built a universal machine tool for Claude Code](https://www.youtube.com/live/EdmuYPBt_EM) | 30:50 |
| 10 | [The capability curve](https://www.youtube.com/live/tP4MGcJ80Y0) | 15:05 |
| 11 | [Architecting for model step-changes: A fireside with Vercel's Guillermo Rauch](https://www.youtube.com/live/bJKdXhnw7NU) | 27:15 |
| 12 | [Building with Claude Managed Agents and Asana AI teammates](https://youtu.be/BrpB-h1e--k) | 24:56 |
| 13 | [Running an AI-native engineering org](https://youtu.be/igO8iyca2_g) | 28:37 |
| 14 | [The thinking lever](https://youtu.be/OXJO4LldSnc) | 24:01 |
| 15 | [Building with Claude on Google Cloud](https://youtu.be/SqHsS737CeA) | 26:29 |
| 16 | [Evaluating and improving Replit Agent at scale](https://youtu.be/snroDwX1-JU) | 27:42 |
| 17 | [Giving coding agents their own computers: How Cursor built cloud agents](https://youtu.be/BbYSGxtsMic) | 14:35 |
| 18 | [Memory and dreaming for self-learning agents](https://youtu.be/RtywqDFBYnQ) | 24:28 |
| 19 | [The expanding toolkit](https://youtu.be/KLCuxMDZSDg) | 21:22 |

---

## _"Too much infos, brain overflowed..."_

Grab this: **[github.com/PiLastDigit/TRIP-workflow](https://github.com/PiLastDigit/TRIP-workflow)**
A minimal, simple & efficient dev workflow for AI coding agents. Basically the nectar juice out of the videos above.
Now go build.
