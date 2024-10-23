
## hugging_face_audio_dataset_creation_TTS
You can create a hugging face audio dataset with this repository
## Creating an English Technical Text-to-Speech Dataset

This Colab notebook demonstrates how to create an English technical Text-to-Speech (TTS) dataset. The process involves downloading technical YouTube videos, extracting audio, transcribing using Whisper, and organizing the data.

## Steps

1.  **Install dependencies:** Install the necessary libraries using `pip install kagglehub git+https://github.com/openai/whisper.git spleeter yt-dlp pydub`. 

2.  **Import Kaggle Data Sources (if applicable):**
    ```python
    import kagglehub
    kagglehub.login()
    manaspkundu_youtube_links_1_path = kagglehub.dataset_download('manaspkundu/youtube-links-1')
    print('Data source import complete.')
    ```

3.  **Download and Process Audio:**
    ```python
    import yt_dlp
    from pydub import AudioSegment
    # ... (rest of the code for downloading, separating voice, converting audio, splitting)
    ```
    * Download audio from YouTube links provided in a text file (`1_links.txt`). 
    * Use `spleeter` to separate voice from other audio sources. 
    * Convert audio to the desired format (mono, 16kHz, 16-bit WAV). 
    * Split audio into smaller chunks (e.g., 4 seconds). 

4.  **Transcribe Audio:**
    ```python
    import whisper
    model = whisper.load_model("base")
    # ... (rest of the code for transcribing audio using Whisper)
    ```
    * Transcribe each audio chunk using the Whisper model. 
    * Save transcriptions as text files. 

5.  **Create Audio-Transcription Pairs:**
    ```python
    import librosa
    import numpy as np
    import json
    # ... (rest of the code for creating and saving audio-transcription pairs)
    ```
    * Load audio data using `librosa`. 
    * Combine audio data and corresponding transcriptions into pairs. 
    * Save pairs as a JSON file (`audio_transcription_pairs.json`). 

6.  **Organize Files:**
    ```python
    import os
    import shutil
    # ... (rest of the code for copying, moving, and organizing files)
    ```
    * Copy all audio and transcription files into a single directory (`all_files`). 
    * Create a `metadata.csv` file with `file_name` and `transcription` columns. 
    * Create a dataset directory (`my_dataset`) with subdirectories (`data`). 
    * Move audio files to `my_dataset/data`. 
    * Move `metadata.csv` to `my_dataset`. 

7.  **Upload to Hugging Face Hub:**
    ```python
    from datasets import load_dataset
    dataset = load_dataset("audiofolder", data_dir="/kaggle/working/my_dataset")
    # ... (rest of the code for logging in and pushing the dataset to the Hub)
    ```
    * Load the dataset using `load_dataset`. 
    * Log in to your Hugging Face account. 
    * Push the dataset to the Hub. 

## Running the code

1.  **Open the Colab notebook:** Click on the provided link to open the notebook in Google Colab.
2.  **Set up environment:** Make sure you have a Google account and are logged in to Colab.
3.  **Run all cells:** Execute all the code cells in the notebook sequentially.
4.  **(Optional) Modify parameters:** You can modify the dataset, model checkpoint, training arguments, and other parameters as needed.
5.  **(Optional) Save a copy:** Save a copy of the notebook to your Google Drive to preserve any changes you make.

This README provides a general overview of the code and steps involved. For more detailed information, please refer to the comments and documentation within the Colab notebook itself.










## 🔗 Links


You can find the Hugging Face Datasets,  kaggle notebbok and the github repository from the bellow Links.

[![Hugging Face Datasets](https://img.shields.io/badge/Hugging%20Face%20Datasets-464646?style=for-the-badge&logo=huggingface&logoColor=white)](https://huggingface.co/datasets/Shabdobhedi/TTS_English_Technical_Terms)

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)]([https://github.com/pratim808/TTS_English_Technical](https://github.com/pratim808/hugging_face_audio_dataset_creation_TTS))

[![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/code/manaspkundu/dataset-english-techn)


