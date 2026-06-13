# Coughvid Analysis
A repo to analyze the COUGHVID dataset.

On my machine (M3 Macbook Air, 16Gb RAM, running on power supply) the run took ~30 minutes

## Data source
Raw data: https://zenodo.org/records/7024894

I used version 3: `public_dataset_v3.zip`, which should contain the labels `status` and `status_SSL` in the `metadata_compiled.csv` file.

Article: https://www.nature.com/articles/s41597-021-00937-4

## How to use this notebook:
The Python library librosa uses FFmpeg as its primary backend to decode audio files. Without FFmpeg being properly installed, the notebook will not be able to process the audio files.

If FFmpeg is not installed it can be installed as follows:

Installation using brew (Mac only):
```
brew install ffmpeg
```

Otherwise from the website:
https://www.ffmpeg.org/


Install the dependencies:
```
pip3 install -r requirements.txt
```

Data can be placed in ./COUGHVIDdataset

Note that the notebook creates additional directories in the workspace to store preprocessed audio files:
- normalized_audio
- trimmed_and_filtered_audio


## Python Libraries
See [requirements.txt](requirements.txt)


## Research Question
Can acoustic features extracted from cough recordings reliably distinguish COVID-19 positive individuals from healthy individuals?