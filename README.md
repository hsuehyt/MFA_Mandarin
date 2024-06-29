# MFA_Mandarin

This repository provides a guide and resources for using the Montreal Forced Aligner (MFA) to extract phonemes and their timings from Mandarin speech audio.

## Prerequisites

1. **Python Installation**: Ensure Python is installed on your system. You can download it from [Python.org](https://www.python.org/).
2. **Git Installation**: Ensure Git is installed on your system. You can download it from [Git-SCM](https://git-scm.com/).
3. **Anaconda or Miniconda**: Ensure you have Anaconda or Miniconda installed. You can download Miniconda from [Miniconda](https://docs.conda.io/en/latest/miniconda.html).

## Installation

1. **Install Miniconda/Conda**

    Download and install Miniconda from [Miniconda Installation](https://docs.conda.io/en/latest/miniconda.html).

2. **Set Up the Environment and Install MFA**

    Open a terminal or command prompt and run the following commands:

    ```bash
    conda config --add channels conda-forge
    conda create -n aligner -c conda-forge montreal-forced-aligner
    conda activate aligner
    ```

3. **Install Required Libraries for Chinese Tokenization**

    ```bash
    pip install jieba pypinyin
    ```

## Prepare Your Project Directory

1. **Create a Project Directory**

    ```bash
    mkdir C:\Users\user\Desktop\mfaProj
    ```

2. **Place Your Files in the Directory**

    - Audio file: `C:\Users\user\Desktop\mfaProj\audio\2024-06-28_10-03-00.mp4`
    - Transcript file: `C:\Users\user\Desktop\mfaProj\transcripts\2024-06-28_10-03-00.txt`
    - Lexicon/Dictionary file: `C:\Users\user\Desktop\mfaProj\dictionary\mandarin_pinyin.dict`
    - Acoustic model: `C:\Users\user\Desktop\mfaProj\acoustic\mandarin_mfa.zip`

    **Note:** Ensure the audio and transcript files have the same name prefix.

3. **Download the Required Files**

    - [Download mandarin_mfa.zip](https://github.com/MontrealCorpusTools/mfa-models/tree/main/acoustic/mandarin/mfa)
    - [Download mandarin_pinyin.dict](https://github.com/MontrealCorpusTools/mfa-models/tree/main/dictionary)

## Run MFA Alignment

To align the audio files using the dictionary and acoustic model, use the following command:

```bash
mfa align --clean --output_format json "C:\Users\user\Desktop\mfaProj\audio" "C:\Users\user\Desktop\mfaProj\dictionary\mandarin_pinyin.dict" "C:\Users\user\Desktop\mfaProj\acoustic\mandarin_mfa.zip" "C:\Users\user\Desktop\mfaProj\aligned"
```

## Directory Structure

Your project directory should look like this:

```
mfaProj/
├── acoustic/
│   └── mandarin_mfa.zip
├── aligned/
├── audio/
│   └── 2024-06-28_10-03-00.mp4
├── dictionary/
│   └── mandarin_pinyin.dict
├── transcripts/
│   └── 2024-06-28_10-03-00.txt
```

## Useful Links

- [Montreal Forced Aligner Documentation](https://montreal-forced-aligner.readthedocs.io/en/latest/getting_started.html)
- [Montreal Forced Aligner GitHub Repository](https://github.com/MontrealCorpusTools/Montreal-Forced-Aligner)
- [MFA Models GitHub Repository](https://github.com/MontrealCorpusTools/mfa-models)
- [PKUSeg Python GitHub Repository](https://github.com/lancopku/pkuseg-python)
- [Git Installation](https://git-scm.com/)
- [Python Installation](https://www.python.org/)
- [Miniconda Installation](https://docs.conda.io/en/latest/miniconda.html)
