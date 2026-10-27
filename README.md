# Tamil-to-Telugu Speech-to-Speech Translation

**Whisper Tamil ASR · IndicTrans2 text translation · VITS/MMS speech synthesis**

An end-to-end pipeline that takes spoken Tamil, transcribes it, translates the text into Telugu, and speaks the result back in Telugu. The recognition and speech-synthesis models were chosen by comparing candidates on standard measures, and the translation stage was scored with BLEU, cosine similarity and ROUGE-L.

![Speech translation pipeline](Images/Pipeline.jpeg)

## How it works

| 1. Speech recognition | 2. Text translation | 3. Speech synthesis |
| --- | --- | --- |
| ![ASR architecture](Images/STT.jpeg) | ![Translation architecture](Images/T2T_arch.png) | ![TTS architecture](Images/TTS.jpeg) |
| Tamil audio → Tamil text with a Whisper model | Tamil text → Telugu text with IndicTrans2 | Telugu text → Telugu speech with a VITS-based MMS model |

## Results

**Speech recognition.** Four Tamil ASR models were compared on Common Voice 11; `Vignesh-M/Whisper-tamil-medium` gave the best score and was used in the pipeline.

| Model | Common Voice 11 |
| --- | ---: |
| **Vignesh-M/Whisper-tamil-medium** | **38.60** |
| vasista22/whisper-tamil-medium | 41.81 |
| AI4Bharat/Indic-Whisper | 44.54 |
| Facebook/Wav2Vec | 71.58 |

**Text translation (IndicTrans2).**

| Measure | Score |
| --- | ---: |
| BLEU | 0.57 |
| Cosine similarity | 0.69597 |
| ROUGE-L | 0.55453 |

**Speech synthesis.** The VITS-based MMS model scored close to natural recordings in mean opinion score (MOS).

| Model | MOS |
| --- | ---: |
| Ground truth recordings | 4.46 |
| **VITS-based MMS** | **4.43** |
| Tacotron 2 | 4.25 |

## Notebooks

- [speech_translation_pipeline.ipynb](speech_translation_pipeline.ipynb): the full speech-to-speech pipeline.
- [tamil_to_telugu_text_translation.ipynb](tamil_to_telugu_text_translation.ipynb): the IndicTrans2 text-translation stage.
- [whisper_fine_tuning.ipynb](whisper_fine_tuning.ipynb): Whisper fine-tuning for Tamil speech recognition.
- [semester-material/speech-translation.ipynb](semester-material/speech-translation.ipynb): an alternative version of the pipeline, with notes on the model choices in [semester-material/README.md](semester-material/README.md).

## Running the notebooks

Open a notebook in Google Colab or Jupyter, run the install cells, and set the input audio and text paths. Keep any access tokens in environment variables rather than in the notebook. Model weights and datasets are downloaded from their original sources and keep their own licences.
