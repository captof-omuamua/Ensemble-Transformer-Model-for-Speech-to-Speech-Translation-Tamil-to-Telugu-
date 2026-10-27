# Tamil-to-Telugu Speech Translation: Alternative Pipeline

**Python · Whisper Tamil · IndicTrans2 · VITS**

An alternative notebook version of the speech-to-speech pipeline. It transcribes Tamil speech with a Whisper model, translates the text into Telugu with IndicTrans2, and synthesizes Telugu speech.

## Workflow

```mermaid
flowchart LR
    N0["Tamil audio"]
    N1["Tamil transcription"]
    N2["Telugu text"]
    N3["Synthesized speech"]
    N0 --> N1 --> N2 --> N3
```

## What is included

- Tamil transcription using a Whisper model
- IndicTrans2 text translation setup
- Text-to-speech model integration
- [speech-translation.ipynb](speech-translation.ipynb), plus a [source archive](source.zip) listed in [SOURCE_INDEX.md](SOURCE_INDEX.md)

## Running it

Open `speech-translation.ipynb` in Google Colab or Jupyter. Install the imported packages, set the audio input paths and model access, and choose the translation direction and speech-synthesis model before running.

## Notes

The project report also describes a Wav2Vec-based recognition variant; this notebook uses Whisper, which scored better in the model comparison shown in the [main README](../README.md#results). More details are in [SOURCE_NOTES.md](SOURCE_NOTES.md).
