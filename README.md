# even_asr

Here are files for creating ASR (automatic speech recognition) Even models.

It is my thesis and project of our expedition team from HSE University.

# Main results:

Models:
- https://huggingface.co/tbkazakova/wav2vec-bert-2.0-even-pakendorf (Wer: 0.5969, Cer: 0.2128) - Multidialectal
- https://huggingface.co/tbkazakova/wav2vec2-large-mms-1b-even-biblical  (Wer: 0.677, Cer: 0.15) - Lamunkhin dialect

Datasets:
| Dataset | Open | Size | Recording quality | Transcription quality | Dialects | Content |
|----------|----------|----------|----------|----------|----------|----------|
| [even_speech_biblical](https://huggingface.co/datasets/tbkazakova/even_speech_biblical) | + | small | great | good | Lamunkhin | high-quality studio recordings of readings of religious texts |
| [even_speech_hse](https://huggingface.co/datasets/tbkazakova/even_speech_hse) | + | very small | poor | medium+ | Bystraja | field data collected by HSE University expedition team |
| [even_speech_pakendorf](https://huggingface.co/datasets/tbkazakova/even_speech_pakendorf) | - | medium | poor |  medium+ | Bystraja, Indigirka, Lamunkhin | field data collected by project (Pakendorf et al. 2007-2012)[1] |


[1]: Brigitte Pakendorf, Dejan Matić, Natalia Aralova & Alexandra Lavrillier. 2007-2012. Documentation of the dialectal and cultural diversity among Evens in Siberia. The Language
Archive. https://Hdl.Handle.Net/1839/00-0000-0000-000F-2DFE-0. 

## Files for model usage (dir: usage):
- [wav2eaf](https://github.com/tbkazakova/even_asr/blob/main/usage/wav2eaf.ipynb) - to recognize long audio and get eaf file
- [recognize_eaf](https://github.com/tbkazakova/even_asr/blob/main/usage/recognize_eaf.ipynb) - to annotate eaf file with ready empty spans

## Training notebooks
- [W2V2_BERT_Even_pakendorf](https://github.com/tbkazakova/even_asr/blob/main/Fine_Tune_W2V2_BERT_Even_pakendorf.ipynb)
- [W2V2_BERT_Even_biblical](https://github.com/tbkazakova/even_asr/blob/main/Fine_Tune_W2V2_BERT_Even_biblical.ipynb)

## Additional notebooks
- [check_model.ipynb](https://github.com/tbkazakova/even_asr/blob/main/check_model.ipynb) - to check model on HSE dataset

## Files for data preprocessing:
**Pakendorf dataset (dir: pakendorf)**
- [get_pakendorf.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/pakendorf/get_pakendorf.ipynb) - to crawl data from The Language Archive project, get links for downloading audio files
- [audio&video_downloading.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/pakendorf/audio&video_downloading.ipynb) - to check what files are downloaded from The Language Archive
- [eaf_formats.csv](https://github.com/tbkazakova/even_asr/blob/main/preproc/pakendorf/eaf_formats.csv) - types of eaf files from project (Aralova et al. 2007-2023)
- [change_wavlinks.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/pakendorf/change_wavlinks.ipynb) - to change links to wav files in eaf files
- [get_spans.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/pakendorf/eaf_formats.csv) - main file of preprocessing - to parse eaf files with different formats, transliterate different latin and cyrillic project variants of orthography into unified cyrillic version, spellcheck, clean data from notes, comments, to save information about timecodes of beginning and ending of the phrases into table of spans
- to delete the longest audio files and files shorter than 1 millisecond
- [get_pakendorf_dataset.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/pakendorf/get_pakendorf_dataset.ipynb) - to cut files and prepare metadata table from table of spans
  
**Biblical dataset (dir: biblical)**
- [voice_activity.ipynb](https://github.com/tbkazakova/even_asr/blob/main/voice_activity.ipynb) - to create eaf files with voice activity markup
- [get_biblical_eaf_annotated.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/biblical/get_biblical_eaf_annotated.ipynb) - to annotate eaf files with empty spans with texts from [biblical_byspans.txt](https://github.com/tbkazakova/even_asr/blob/main/preproc/biblical/biblical_byspans.txt) (manually divided into phrases) 
- [get_biblical_dataset.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/biblical/get_biblical_dataset.ipynb) - to cut files and prepare metadata table from table of spans

**HSE dataset (dir: hse)**
- [eafs2dataset.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/hse/eafs2dataset.ipynb)
  
## Simple useful functions (dir: simple_func)
- [audio_length.ipynb](https://github.com/tbkazakova/even_asr/blob/main/audio_length.ipynb) - to count audio length
- [change_tempo.ipynb](https://github.com/tbkazakova/even_asr/blob/main/change_tempo.ipynb) - to change audio tempo
- [mp32wav.ipynb](https://github.com/tbkazakova/even_asr/blob/main/mp32wav.ipynb) - to convert mp3 to wav
- [cut_audio.ipynb](https://github.com/tbkazakova/even_asr/blob/main/cut_audio.ipynb) - to cut audio

