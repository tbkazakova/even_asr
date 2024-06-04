# even_asr

Here are files for creating ASR (automatic speech recognition) Even models.

It is my thesis and project of our expedition team from HSE University.

# Main results:

Models:
- https://huggingface.co/tbkazakova/wav2vec-bert-2.0-even-biblical

Datasets:
| Dataset | Size | Recording quality | Content |
|----------|----------|----------|----------|
| [even_speech_biblical](https://huggingface.co/datasets/tbkazakova/even_speech_biblical) | small | great | high-quality studio recordings of readings of religious texts |
| [even_speech_hse](https://huggingface.co/datasets/tbkazakova/even_speech_hse) | medium | poor | field data collected by HSE University expedition team |
| [even_speech_pakendorf](https://huggingface.co/datasets/tbkazakova/even_speech_pakendorf) | medium | poor | field data collected by project (Aralova et al. 2007-2023)[1] |


[1]: Natalia Aralova, Brigitte Pakendorf, Alexandra Lavrillier, Dejan Matić, Katharina Gernet, Tat'jana Vasil'evna Zakharova, Raisa Petrovna Kuzmina, and Luise Zippel (2007 - 2023). Collection "Even". The Language Archive. https://hdl.handle.net/1839/07210104-91d6-4133-b067-b21eadc35f9a

## Training notebooks
- [W2V2_BERT_Even_biblical](https://github.com/tbkazakova/even_asr/blob/main/Fine_Tune_W2V2_BERT_Even_biblical.ipynb)

## Files for data preprocessing:
**Pakendorf dataset (dir: pakendorf)**
- [get_pakendorf.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/pakendorf/get_pakendorf.ipynb) - to crawl data from DOBES project, get links for downloading audio files
- [audio&video_downloading.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/pakendorf/audio&video_downloading.ipynb) - to check what files are downloaded from DOBES
- [eaf_formats.csv](https://github.com/tbkazakova/even_asr/blob/main/preproc/pakendorf/eaf_formats.csv) - types of eaf files from project (Aralova et al. 2007-2023)
- [get_pakendorf_dataset.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/pakendorf/get_pakendorf_dataset.ipynb) - to cut files and prepare metadata table from table of spans
- 
**Biblical dataset (dir: biblical)**
- [voice_activity.ipynb](https://github.com/tbkazakova/even_asr/blob/main/voice_activity.ipynb) - to create eaf files with voice activity markup
- [get_biblical_eaf_annotated.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/biblical/get_biblical_eaf_annotated.ipynb) - to annotate eaf files with empty spans with texts from [biblical_byspans.txt](https://github.com/tbkazakova/even_asr/blob/main/preproc/biblical/biblical_byspans.txt) (manually divided into phrases) 
- [get_biblical_dataset.ipynb](https://github.com/tbkazakova/even_asr/blob/main/preproc/biblical/get_biblical_dataset.ipynb) - to cut files and prepare metadata table from table of spans
  
## Simple useful functions (dir: simple_func)
- [audio_length.ipynb](https://github.com/tbkazakova/even_asr/blob/main/audio_length.ipynb) - to count audio length
- [change_tempo.ipynb](https://github.com/tbkazakova/even_asr/blob/main/change_tempo.ipynb) - to change audio tempo
- [mp32wav.ipynb](https://github.com/tbkazakova/even_asr/blob/main/mp32wav.ipynb) - to convert mp3 to wav
- [cut_audio.ipynb](https://github.com/tbkazakova/even_asr/blob/main/cut_audio.ipynb) - to cut audio
-  

