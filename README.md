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


## Step 3: Run the code in each module

### 1.1 ATST evaluation
```bash
bash ATST-SEA/audiossl/methods/atstframe/shell/downtream/finetune_as_strong/test_frame_atst.bash
```

### 1.2 Diff-SV evaluation
```bash
bash DIFF-SV-SEA/code/diff_sv/main.py
```

### 1.3 EResNetV2 evaluation
```bash
bash RESNET-SEA/egs/voxceleb/sv-eres2netv2/run.sh
```

### 1.4 Baseline evaluation
```bash
python VPC-SEA/run_anonymization.py --config {choice_of_baseline}
```

Please cite these papers if you happen to use the codes:

```BibTeX
@article{chen20243d,
  title={3D-Speaker-Toolkit: An Open Source Toolkit for Multi-modal Speaker Verification and Diarization},
  author={Chen, Yafeng and Zheng, Siqi and Wang, Hui and Cheng, Luyao and others},
  booktitle={ICASSP},
  year={2025}
}
```

```
@article{kim2023diff,
  title={Diff-SV: A Unified Hierarchical Framework for Noise-Robust Speaker Verification Using Score-Based Diffusion Probabilistic Models},
  author={Kim, Ju-ho and Heo, Jungwoo and Shin, Hyun-seo and Lim, Chan-yeong and Yu, Ha-Jin},
  journal={arXiv preprint arXiv:2309.08320},
  year={2023}
}
```

