# Code w/ Claude — San Francisco 2026 · Full Transcripts

Anthropic uploaded the complete session recordings from their **Code w/ Claude** event in San Francisco — ~8 hours across **19 videos**, free on YouTube. This folder holds a clean, readable transcript of **all 19** talks, each with an AI-generated thesis + key-points summary at the top.

Talks span keynotes, workshops, and demos, featuring Dario & Daniela Amodei, Boris Cherny (creator of Claude Code), Guillermo Rauch (Vercel), Jarred Sumner (Bun), and teams from Cognition, Gamma, Harvey, Datadog, Asana, Google Cloud, Replit, and Cursor.

## How these were made

Each transcript was produced from the YouTube audio with:

- **[Deepgram Nova-3](https://deepgram.com/)** — pre-recorded transcription with smart formatting, punctuation, and paragraphing, automatic language detection, no chunking (handles long audio natively). Blazing fast — the opening keynote's 47 minutes transcribed in ~5 seconds (530× realtime). This is the base text: its wording, punctuation and paragraphing are what you read.
- **[ElevenLabs Scribe v2](https://elevenlabs.io/)** — a second transcription of the same audio, with keyterm prompting for this event's vocabulary. Used only to *correct* the base text, never to replace it: the two are aligned token by token and Scribe's reading is adopted only where it supplies a known-correct domain term or fixes a known corruption. Also supplies speaker diarization and the word-level timings behind the timestamps and chapters.
- **Gemini Flash-Lite** — generates the `## Thesis` + `## Key Points` summary block at the top of each file.

**Why the second pass.** Nova-3 is excellent on ordinary speech but does not know the product names this event is about. Across all 19 talks it corrupted 22.96% of domain terms (163 of 710) — Claude's own name appears as *Cloud*, *quad*, *Clot* and *clawed*, and CodeRabbit is spelled three different wrong ways. Scribe v2 with a 116-term keyterm list has an observed corruption rate of 0.99% (11 of 1107), and the corrected text you are reading, 0.1% (1 of 1019).

Those three rates are **not a like-for-like accuracy comparison** and should not be read as one. Each is the observed corruption rate among *that source's own* recognised domain-term candidates, so the denominators differ (710 / 1107 / 1019) and a source that simply fails to produce a term is not penalised. There is no ground-truth transcript for this material, so none of this is WER. The corruption vocabulary was derived from Deepgram's output, which biases it against Deepgram. And the final 0.1% is an in-sample residual measured by the same detector that chose the corrections, so it says the corrections were applied, not that the result is 99.9% correct.

**Two layers of correction, not one.** Most substitutions are automatic: the token alignment above, applied under a fixed rule. A smaller set — 27 in the transcripts, plus the summary fixes — was adjudicated individually, because the rule cannot reach them. Those cover names that only another speaker says out loud, spellings both engines get wrong the same way, and terms established outside the audio. Every one of them is listed below rather than folded silently into the automatic pass.

<details>
<summary><strong>The 27 individually adjudicated substitutions</strong> (click to expand)</summary>

Each of these was decided one at a time, because the alignment rule cannot reach it.
Shown in shipped form, after the roster pass below.

| Talk | Base text | Shipped |
|---|---|---|
| 1 | `Thanks Scott.` | `Thanks, Cat.` |
| 1 | `Thanks, Anmi.` | `Thanks, Ami.` |
| 1 | `You heard a little bit from Omni as well.` | `You heard a little bit from Ami as well.` |
| 1 | `Ansho and Caitlin's agents` | `Angela and Katelyn's agents` |
| 2 | `15 year old's like carnivore.` | `15-year-old who's doing a summer job, a summer carnival ride.` |
| 2 | `Daniella` | `Daniela` |
| 2 | `Danielle` | `Daniela` |
| 2 | `Sorry, Daria.` | `Sorry, Dario.` |
| 3 | `localhost three thousand and two` | `localhost:3002` |
| 4 | `Jared Sumner` | `Jarred Sumner` |
| 4 | `classic Jared doing work` | `classic Jarred doing work` |
| 4 | `if Jared types` | `if Jarred types` |
| 5 | `you could trust them with stat six as well` | `you could trust them with Statsig as well` |
| 6 | `backslash cloud dash API` | `/claude-api` |
| 7 | `three five, three six` | `3.5, 3.6` |
| 7 | `Dini Patiha` | `Deeni Fatiha` |
| 7 | `Harvey Nico Gruppen` | `Harvey, Niko Grupen` |
| 7 | `explosive year for Cloud Agents` | `explosive year for Claude Agents` |
| 7 | `like Cloud Agents are kind of becoming` | `like Claude Agents are kind of becoming` |
| 13 | `to go away I'm old` | `in the way I move` |
| 13 | `Boris and Jared had their session` | `Boris and Jarred had their session` |
| 15 | `directly consuming cloud code through the MCP server` | `directly consuming Claude Code through the MCP server` |
| 15 | `and it will have cloud code to figure it out` | `and it will have Claude Code to figure it out` |
| 15 | `You can just leverage Cloud Code and this MCP server` | `You can just leverage Claude Code and this MCP server` |
| 18 | `pivot over to the Cloud console` | `pivot over to the Claude console` |
| 18 | `spins up within the Cloud console` | `spins up within the Claude console` |
| 18 | `dreaming in the Cloud Managed Agents API` | `dreaming in the Claude Managed Agents API` |

And the canonical person names, applied to every talk, from the session roster:

| Talk | Heard as | Roster |
|---|---|---|
| all | `Diane` | `Dianne` |
| all | `Angela Zhang` | `Angela Jiang` |
| all | `Caitlin` | `Katelyn` |
| all | `Kat` | `Cat` |
| all | `Dixon` | `Dickson` |
| all | `Deni` | `Deeni` |
| all | `Nico` | `Niko` |
| all | `Grupin` | `Grupen` |
| all | `Arnav` | `Arnab` |
| all | `Sesh Nala` | `Sesh Nalla` |
| all | `Fiona Feng` | `Fiona Fung` |
| all | `Matt Blyfer` | `Matt Bleifer` |

</details>

**Person names come from the roster, not the audio.** Speaker names are taken from the official [Code w/ Claude session pages](https://claude.com/code-with-claude/san-francisco); the transcript is used only to work out which speaker is which, never how a name is spelled. Names are the one class where cross-engine agreement proves nothing: both engines mishear the same sounds the same way, and every candidate is a plausible name. The base transcripts offer *Angela Zhang*, *Caitlin*, *Dixon Tsai* and *Nico Grupin* for **Angela Jiang**, **Katelyn Lesse**, **Dickson Tsai** and **Niko Grupen**, and nothing inside the audio tells you which is right.

**What is editorial.** The chapter titles are written rather than transcribed. Where a speaker announces their own structure the titles follow their words; where a talk has no verbal structure the boundaries are an editorial call. Neither YouTube nor the uploader provides chapters for any of these videos. Where two engines disagree on a name and the audio does not settle it, the base text is left alone rather than guessing. Two terms are corrected from outside the audio, because both engines make the same mistake: the Replit session's *ViBench* and *vibe coding*, which both engines hear with a *b*.

Every `.txt` file is structured as:

```
Transcript: <title>          ← header: language, paragraph count, RTFx, processing time
────────────────────────────
## Thesis / ## Key Points     ← AI summary
## Chapters                   ← timestamped index, deep-linked into the video
════════════════════════════
TRANSCRIPT                    ← full readable transcript, paragraph-formatted
```

Inside the transcript, `[m:ss]` prefixes mark position in the video (at most two per
minute), and `NAME:` marks a change of speaker in the ten multi-speaker sessions.

**On the speaker labels.** Who is speaking comes from Scribe's diarization, mapped onto the
people listed for that session on Anthropic's published roster; transcript content is used
only to work out which rostered person a given voice is. It is machine-assigned and not
verified against the audio, so treat a label as a strong hint rather than a citation. Where
a turn's own words contradict the diarization — someone naming themselves in the third
person, or handing the floor to the person the diarization thinks is speaking — the label
follows the content instead. Labels sit at the
word where the turn changes, which is often mid-paragraph, because Deepgram's paragraph
breaks do not fall on speaker turns.

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
