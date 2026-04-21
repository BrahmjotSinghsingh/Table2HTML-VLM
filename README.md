# Image-to-HTML Table Generator: VLM Fine-Tuning

## Overview
This project fine-tunes a Vision-Language Model (VLM) to automatically generate HTML representations of tables directly from images. It leverages the **Unsloth** library for highly efficient, memory-optimized LoRA fine-tuning, using the Qwen2.5-VL architecture.

## Features
- **Custom Data Processing**: Converts image-HTML pairs into standard conversation formats required for chat-based vision models.
- **Efficient Finetuning**: Utilizes `unsloth` and `trl`'s `SFTTrainer` to perform memory-efficient Parameter-Efficient Fine-Tuning (PEFT) via LoRA.
- **Inference & Cleaning Pipeline**: Includes a custom inference pipeline that takes an image of a table, prompts the model, and uses Regex to strip Markdown and output clean, renderable HTML.

## Dataset
The dataset used for fine-tuning is **[apoidea/pubtabnet-html](https://huggingface.co/datasets/apoidea/pubtabnet-html)**, sourced from the Hugging Face Hub.
It consists of images of tables and their corresponding HTML code. The notebook maps the relevant data features into a conversational format:
* **User**: `[Image]` + "Generate the HTML representation for this table image."
* **Assistant**: `[HTML Code]`

## Installation
To run this notebook, you will need a GPU-enabled environment (like Kaggle or Google Colab) and the following primary dependencies:
```bash
pip install unsloth transformers datasets trl Pillow
