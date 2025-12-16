# Sound-Event-Anonymization
Official implementation of the paper "SOUND EVENT ANONYMIZATION: A FRAMEWORK FOR EVALUATING THE PRIVACY-UTILITY TRADE-OFF"

## Step 1: Environment setup
Since the project contains many modules, I suggest to use conda for each module.

### 1.1 Install conda
https://docs.conda.io/projects/conda/en/stable/user-guide/install/index.html

### 1.2 Create a conda environment for each module
ATST evaluation environment
```bash
cd ATST-SEA
# create conda env for ATST with the name audiossl_clone
conda env create -f environment.yml 
```
Please go to https://huggingface.co/hungln0803/audiossl to get the pretrained model.

Diff-SV evaluation environment
```bash
cd DIFF-SV-SEA
conda create -n diff_sv python==3.8
conda activate diff_sv
pip install -r requirements.txt
```
EResNetV2 evaluation environment
```bash
cd RESNET-SEA
conda create -n resnet python==3.8.20
conda activate resnet
pip install -r requirements.txt
```

Baseline environment. Please contact the VPC2024 organizers for the password when running 01_download_data_model.sh
```bash
cd VPC-SEA
bash 00_install.sh
bash 01_download_data_model.sh
```

## Step 2: Download dataset
Please go to https://huggingface.co/datasets/hungln0803/Sound-Event-Anonymization and download the repo.

```
unzip audioset_strong.zip
unzip enroll_trial.zip
```


