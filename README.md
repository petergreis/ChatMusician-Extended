# 🎼 ChatMusician Extended - fine tuning and evaluation using Mozart and Scarlatti

![alt Mozart and Scarlatti delegate](images/Mozart_Scarlatti.webp)

[💻 **ChatMusician Code**](https://github.com/hf-lin/ChatMusician) | [**🤖 Chat Model**](https://huggingface.co/m-a-p/ChatMusician) | [**🤖 Base Model**](https://huggingface.co/m-a-p/ChatMusician-Base)

## 🔔News

## Introduction

While ChatMusician is an impressive offering, we thought it might be interesting to see if the model could be extended by further training with baroque and classical material.
We introduce **ChatMusician Extended**, **an open-source LLM that extends ChatMusician**.

## Training Data

ChatMusician Extended is trained on corpus cultivated from [Art der Fuge](www.artderfuge.com). An initial 157 Mozart and 555 Scarlatti compositions were used as separate fine tuning data sets followed by each composition being transposed into the other 11 keys resulting in 1286 and 6211 files respectively.

## Training Procedure

Following the [initial hyperparameters](https://github.com/hf-lin/ChatMusician?tab=readme-ov-file#training-procedure) from ChatMusician the fine tuning was executed on resources from [Paperspace's Gradient](https://www.paperspace.com/artificial-intelligence) and [Google Colab](https://colab.research.google.com). Both NVidia A100 and A6000 resources were used.

## Evaluation

1. Music understanding abilities are evaluated on the [MusicTheoryBench](https://huggingface.co/datasets/m-a-p/MusicTheoryBench).

## Requirements

As with the initial project:

- Python 3.8 and above
- Pytorch 2.0 and above are recommended

For Windows and Linux environments:

- CUDA 11.4 and above are recommended
- Deepspeed 0.10 and above are recommended

For macOS and MLX evaluation:

- [mlx](https://ml-explore.github.io/mlx/build/html/index.html) 0.11.1 and above
- mlx-lm 0.10.0 and above are recommended

To avoid certain non-implementations errors in pytorch and macOS (RuntimeError: MPS does not support cumsum op with int64 input), install the latest pytorch nightly:

```bash
conda install pytorch-nightly::pytorch torchvision torchaudio -c pytorch-nightly

#  or

pip3 install --pre torch torchvision torchaudio --index-url https://download.pytorch.org/whl/nightly/cpu

# Check - or use pip list
conda list | grep torch
pytorch                   2.4.0.dev20240422        py3.12_0     pytorch-nightly
torchaudio                2.2.0.dev20240422        py312_cpu    pytorch-nightly
torchvision               0.19.0.dev20240422       py312_cpu    pytorch-nightly
```

Notably this also adds bfloat16 support to macOS/MPS

### MLX notes

After fine tuning and merging, the resulting model will be need to be converted to a [supported format](https://ml-explore.github.io/mlx/build/html/python/_autosummary/mlx.core.load.html) for MLX. A local capable [convert script](https://github.com/petergreis/ChatMusician-Extended/blob/main/convert_to_safetensors.py) has been included here as part of this repository.

## Inference

### web demo (with audio)

Then launch a gradio demo:

```bash
cd ChatMusician/
python model/infer/chatmusician_web_demo.py -c "m-a-p/ChatMusician" --server_port 8890
```

or macOS accelerated with mlx:

```bash
cd ChatMusician/
python model/infer/chatmusician_web_demo_mlx.py -c "m-a-p/ChatMusician" --server_port 8890
```

Prompt example:

```

```

### inference locally

## Training

### Data Preprocessing

## Limitations
