# North_whale_dcase_open

# DAAPNet: Dynamic Attention-Asymmetric Perceptron Network for Overlapping Sound Event Detection

## 🚀 Access the Code | 获取代码

This repository serves as an introduction to the paper. **The complete source code and implementation details are hosted in the following repository:**

👉 **[Click here to view the Source Code](https://github.com/NinaGel/dcase_north_whale_open)** 👈

---

## 📖 Abstract

Detecting overlapping sound events in complex acoustic environments presents a significant challenge, especially under low Signal-to-Noise Ratio (SNR) conditions where temporal and spectral variations hinder the distinction of individual events.

To address this, we propose the **Dynamic Attention-Asymmetric Perceptron Network (DAAPNet)**. DAAPNet is designed to capture deep temporal and spectral variations through three novel modules, achieving state-of-the-art performance on both bioacoustic (Whale) and domestic (DCASE) datasets.

## 💡 Key Contributions & Methodology

DAAPNet integrates three core modules to handle overlapping acoustic features efficiently:

### 1. Bidirectional Asymmetric Convolution (BA-Conv)
* **Mechanism:** Uses asymmetric convolution kernels ($1\times3$ and $3\times1$) in separate pathways.
* **Benefit:** Decouples temporal and spectral patterns to separate overlapping acoustic features while maintaining high computational efficiency and low parameter count.

### 2. Time-Frequency Dynamic Perceptron (TFDP)
* **Mechanism:** Processes signals through three stages: **Expansion**, **Grouping**, and **Cross-Shifting Perception**.
* **Benefit:** Adapts dynamically to variations in both time and frequency domains, enhancing feature discriminability in complex environments.

### 3. Dynamic Dense Synthesizer Attention (DDSA)
* **Mechanism:** Extends traditional attention by using **multi-scale context sizes** with learnable fusion weights.
* **Benefit:** Effectively models both brief (e.g., gunshots) and extended (e.g., whale moans) acoustic events. It reduces the quadratic complexity of self-attention to linear complexity ($O(n)$).

## 📊 Experimental Results

We evaluated DAAPNet on two overlapping sound event datasets under various SNR levels:
1.  **North Atlantic Right Whale (NARW) Dataset** (Synthesized overlapping)
2.  **DCASE Domestic Sound Event Dataset** (Synthesized based on DCASE 2021/2023 protocol)

**Highlights:**
* **Low SNR Robustness:** Outperforms state-of-the-art methods (such as Conformer and FAF-Filt) by **10.7% in PSDS** at very low SNR conditions.
* **Efficiency:** Achieves superior performance with significantly lower computational cost (FLOPs) compared to Transformer-based models like Conformer.

| Model | Parameters (M) | FLOPs (G) | PSDS (High SNR) | PSDS (Low SNR) |
| :--- | :---: | :---: | :---: | :---: |
| Conformer | 25.53 | 15.25 | 0.751 | 0.395 |
| FAF-Filt | 5.73 | 23.39 | 0.743 | 0.560 |
| **DAAPNet (Ours)** | **6.26** | **1.93** | **0.779** | **0.607** |

*> Note: Metrics above are based on the Whale dataset experiments.*
