# sd-edge-tts

Speech dispatcher module that uses Microsoft Edge's TTS service as backend.

Supports Chinese (Mandarin, Cantonese, Taiwanese), Japanese, Korean, and English out of the box. Add any other language by editing `speech-dispatcher/modules/edge-tts-generic.conf` — see available voices with `edge-tts --list-voices`.

## Dependencies

1. **speech-dispatcher** — installed and configured (socket activation enabled, etc.)
2. **mpv** — audio playback backend
3. [**edge-tts**](https://github.com/rany2/edge-tts) — Python package, available in `PATH`

## Installation

1. Clone or download this repository.
2. Copy the `speech-dispatcher` folder to `~/.config/`:
   ```bash
   cp -r speech-dispatcher ~/.config/
   ```
3. Restart Speech Dispatcher:
   ```bash
   killall speech-dispatcher
   speech-dispatcher &
   ```

## Verification

```bash
# Test Chinese
spd-say -o edge-tts-generic -l zh "你好世界"

# Test English
spd-say -o edge-tts-generic "Hello, this is Edge TTS."

# Test Japanese
spd-say -o edge-tts-generic -l ja "こんにちは"

# List all available voices
edge-tts --list-voices
```

Open Firefox, enable Reader Mode on any article, and TTS should work through the default module.
