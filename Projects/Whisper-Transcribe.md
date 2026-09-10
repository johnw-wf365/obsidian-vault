# Whisper Transcribe Skill

**Installed:** 2026-09-10
**Location:** `/opt/whisper.cpp/`
**Models:** `/opt/whisper.cpp/models/`
**Wrapper:** `/usr/local/bin/whisper-transcribe`
**Skill:** `skills/media/whisper-transcribe/SKILL.md`

---

## What It Does

Local video and audio transcription using whisper.cpp. Runs 100% on-device — no API keys, no cloud, no cost.

## Quick Start

```bash
whisper-transcribe <file> [model] [format]
```

**Examples:**
```bash
whisper-transcribe meeting.mp4              # video → text
whisper-transcribe podcast.mp3 base         # audio → text (better accuracy)
whisper-transcribe video.mp4 tiny srt       # video → subtitles
whisper-transcribe audio.wav base json      # audio → JSON with timestamps
```

## Models Available

| Model | Size | Speed | Accuracy |
|-------|------|-------|----------|
| tiny | 75MB | Fastest | Good |
| base | 140MB | Fast | Better |
| small | 500MB | Medium | Great |
| medium | 1.5GB | Slow | Excellent |
| large-v3 | 3GB | Slowest | Best |

## Supported Formats

**Audio:** wav, mp3, flac, ogg, m4a, aac
**Video:** mp4, mkv, avi, mov, webm, flv, wmv

## Output Formats

- `text` — Plain text
- `srt` — SubRip subtitles
- `vtt` — WebVTT subtitles
- `json` — Full JSON with timestamps
- `csv` — CSV with timestamps

---

## Installation Details

- **Binary:** Pre-built `whisper-bin-ubuntu-x64.tar.gz` from whisper.cpp releases
- **Model:** `ggml-tiny.bin` (75MB) from HuggingFace
- **Dependencies:** ffmpeg (already installed at `/usr/bin/ffmpeg`)

---

## Related

- [[Skills]]
- [[Whisper.cpp Upstream](https://github.com/ggml-org/whisper.cpp)]
