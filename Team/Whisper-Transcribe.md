# Whisper Transcribe — Available to All Agents

**Skill:** `skills/media/whisper-transcribe/SKILL.md`
**Wrapper:** `/usr/local/bin/whisper-transcribe`
**Location:** `/opt/whisper.cpp/`

## Quick Reference

```bash
whisper-transcribe <file> [model] [format]
```

**Models:** tiny (default), base, small, medium, large-v3
**Formats:** text (default), srt, vtt, json, csv

## When to Use

- Transcribing meeting recordings
- Converting video content to text
- Generating subtitles for videos
- Processing podcast episodes
- Any speech-to-text task

## Examples

```bash
whisper-transcribe meeting.mp4              # meeting → text
whisper-transcribe podcast.mp3 base         # podcast → text (better)
whisper-transcribe video.mp4 tiny srt       # video → subtitles
whisper-transcribe audio.wav base json      # audio → JSON with timestamps
```

## Notes

- No API keys needed — runs locally
- Video files: audio auto-extracted via ffmpeg
- For quick tasks: use `tiny` model
- For accuracy: use `base` or `small` model
- Large videos: stick with `tiny` or `base` for speed

## Related

- [[Skills]]
- [[Projects/Whisper-Transcribe]]
