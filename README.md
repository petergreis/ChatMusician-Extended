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

Following the initial hyperparaters from ChatMusician the fine tuning was executed on resources from [Paperspace's Gradient](https://www.paperspace.com/artificial-intelligence) and [Google Colab](https://colab.research.google.com). Both NVidia A100 and A6000 resources were used.

## Evaluation

1. Music understanding abilities are evaluated on the [MusicTheoryBench](https://huggingface.co/datasets/m-a-p/MusicTheoryBench).

## Requirements

- Python 3.8 and above
- Pytorch 2.0 and above are recommended

For Windows and Linux environments:

- CUDA 11.4 and above are recommended
- Deepspeed 0.10 and above are recommended

For macOS and MLX evaluation:

- [mlx](https://ml-explore.github.io/mlx/build/html/index.html) 0.11.1 and above
- mlx-lm 0.10.0 and above are recommended

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
