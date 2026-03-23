# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 專案概述

本專案是一本深度學習書籍的程式碼倉庫，共 30 章（ch01–ch30），每章對應一篇經典論文，以 PyTorch 實作。所有內容（markdown、註解、docstring）使用繁體中文（台灣用語）。

## 架構

- 每章一個目錄（`ch01/` ~ `ch30/`），內含：
  - 一個主要 Jupyter Notebook（`*_pytorch.ipynb`），為該章的完整實作
  - 說明用圖片（`.png`）
  - `paper_qrcode.png`：連結到原論文
- 無獨立 Python 模組、無 `requirements.txt`、無 `pyproject.toml`
- 所有程式碼自包含於 notebook 中，不跨章引用

## 技術棧

- **框架**：PyTorch（主要）、matplotlib（視覺化）、NumPy
- **環境**：Jupyter Notebook（支援 Colab、VSCode、本地環境）
- **Python kernel**：`python3 (ipykernel)`
- **中文字型**：每個 notebook 開頭有跨平台中文字型自動偵測與設定邏輯（Heiti TC、PingFang TC、Noto Sans CJK TC 等）

## 常用指令

```bash
# 執行單一 notebook
jupyter nbconvert --to notebook --execute ch01/complexity_pytorch.ipynb

# 在瀏覽器中編輯
jupyter notebook ch01/complexity_pytorch.ipynb

# 安裝依賴（使用 uv）
uv pip install torch numpy matplotlib jupyter
```

## 章節與論文對照

| 章節 | 主題 | Notebook |
|------|------|----------|
| ch01 | 複雜動力學第一定律 | complexity_pytorch.ipynb |
| ch02 | Char-RNN | char_rnn_pytorch.ipynb |
| ch03 | LSTM | lstm_pytorch.ipynb |
| ch04 | RNN Dropout | rnn_dropout_pytorch.ipynb |
| ch05 | 剪枝（Pruning） | pruning_pytorch.ipynb |
| ch06 | Pointer Networks | pointer_networks_pytorch.ipynb |
| ch07 | AlexNet | alexnet_pytorch.ipynb |
| ch08 | Seq2Seq Sets | seq2seq_sets_pytorch.ipynb |
| ch09 | GPipe | gpipe_pytorch.ipynb |
| ch10 | ResNet | resnet_pytorch.ipynb |
| ch11 | Dilated Convolutions | dilated_conv_pytorch.ipynb |
| ch12 | GNN | gnn_pytorch.ipynb |
| ch13 | Transformer | transformer_pytorch.ipynb |
| ch14 | Bahdanau Attention | bahdanau_attention_pytorch.ipynb |
| ch15 | Identity ResNet | identity_resnet_pytorch.ipynb |
| ch16 | Relation Networks | relation_networks_pytorch.ipynb |
| ch17 | VAE | vae_pytorch.ipynb |
| ch18 | Relational RNN | relational_rnn_pytorch.ipynb |
| ch19 | Coffee Automaton | coffee_automaton_pytorch.ipynb |
| ch20 | Neural Turing Machine | neural_turing_machine_pytorch.ipynb |
| ch21 | CTC Speech | ctc_speech_pytorch.ipynb |
| ch22 | Scaling Laws | scaling_laws_pytorch.ipynb |
| ch23 | GPT-3 | gpt3_pytorch.ipynb |
| ch24 | Vision Transformer | vit_pytorch.ipynb |
| ch25 | DDPM | ddpm_pytorch.ipynb |
| ch26 | CLIP | clip_pytorch.ipynb |
| ch27 | AlphaFold | alphafold_pytorch.ipynb |
| ch28 | DALL-E | dalle_pytorch.ipynb |
| ch29 | Stable Diffusion | stable_diffusion_pytorch.ipynb |
| ch30 | InstructGPT / RLHF | instructgpt_pytorch.ipynb |

## 開發慣例

- Notebook 命名格式：`{主題}_pytorch.ipynb`
- 每個 notebook 開頭第一個 cell 是 markdown 標題與論文簡介
- 第二個 cell 通常是跨平台中文字型設定（可直接複製既有章節的模板）
- 隨機種子固定（`torch.manual_seed(42)`）以確保可重現性
- 圖表使用中文標題與標籤
