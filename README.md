# HarMeme

## This project uses [this](https://github.com/di-dimitrov/mmf) fork of Facebook's MMF framework.

#### !!! The **DATASET** is located in [this repository](https://github.com/di-dimitrov/mmf) under the following paths: 
#### /data/datasets/memes/defaults/annotations (labels) 
#### /data/datasets/memes/defaults/images (memes)
#### /data/datasets/memes_tgt/defaults/annotations (target labels) `dataset folder is same as the other task`

#### !!! Please make sure that CUDA 10.2+ is installed on you machine.
#### !!! Linux OS is recommended, otherwise you would face installation problems.
#### !!! We are using the open source Multimodal Framework developed by FacebookResearch: https://mmf.sh/

### Follow these steps to get all the code ready and running:
1. Prerequisites - generating image caption features for VisualBERT and ViLBERT:
    1. Clone [this repository](https://github.com/di-dimitrov/mmf) and go to './mmf' path
    2. Install MMF according to the instructions here: https://mmf.readthedocs.io/en/website/notes/installation.html
    3. Install the following packages: 'pip install yacs, opencv-python, cython' (if using 'pip', any package manager works)
    4. Clone vqa-maskrcnn-benchmark repository: https://gitlab.com/vedanuj/vqa-maskrcnn-benchmark
        1. Run 'python setup.py build'
        2. Run 'python setup.py develop'
        3. Run the feature extraction script from the following path: 'mmf/tools/scripts/features/extract_features_vmb.py'
        4. After feature extraction is done convert the features to a .mdb file with the following script: 'mmf/tools/scripts/features/extract_features_vmb.py'
        5. Rename the .mdb features file to 'deceptron.lmdb' and move it to '/root/.cache/torch/mmf/data/datasets/memes/defaults/features/'
2. Running the models - open **'HarMeme.ipynb'** and **run** the code inside.
