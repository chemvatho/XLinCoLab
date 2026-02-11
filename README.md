# Experimental Linguistics Analysis Pipelines

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

Comprehensive data analysis pipelines for experimental linguistic research, covering EEG, speech recordings, eye-tracking, and reaction time studies. These notebooks demonstrate reproducible workflows for processing and analyzing diverse experimental data types commonly used in phonetics, psycholinguistics, and cognitive science research.

**Author:** Chem Vatho, PhD  
**Affiliation:** University of Cologne, IfL – Phonetik  
**Contact:** chemvatho@gmail.com

---

## 📋 Overview

This repository contains analysis pipelines developed for the **Experimental Service Hub** at the Data Center for the Humanities (DCH), University of Cologne. Each notebook provides a complete, reproducible workflow from data loading to statistical analysis and visualization.

<img src="https://github.com/chemvatho/XLinCoLab/blob/main/speech_recording_analysis/teang_careful-4.png" alt="diphthong" width="800"/>


| Pipeline | Data Type | Key Methods |
|----------|-----------|-------------|
| [EEG Analysis](#eeg-analysis) | EEG recordings | ERP analysis, time-frequency decomposition |
| [Speech Recording](#speech-recording-analysis) | Audio files | F0 extraction, formant analysis, voice quality |
| [Eye-tracking](#eye-tracking-analysis) | Gaze data | Fixation analysis, time course visualization |
| [Reaction Time](#reaction-time-analysis) | Behavioral data | RT distributions, mixed-effects modeling |

---

## 🧠 EEG Analysis

**Notebook:** [`EEG_Analysis_Pipeline.ipynb`](./Notebook/EEG_Analysis_Pipeline.ipynb)

A comprehensive pipeline for processing electroencephalography (EEG) data in linguistic experiments, with focus on event-related potentials (ERPs) relevant to language processing.

### Features
- **Preprocessing:** Bandpass filtering (0.1–30 Hz), baseline correction, artifact rejection
- **ERP Analysis:** N400 and P600 component extraction for semantic/syntactic processing
- **Time-Frequency Analysis:** Morlet wavelet decomposition for oscillatory dynamics
- **Statistical Analysis:** T-tests, effect sizes (Cohen's d), condition comparisons
- **Visualization:** Multi-channel ERP plots, topographic maps, TFR spectrograms

<img src="https://github.com/chemvatho/XLinC-Lab/blob/main/EEG_results/erp_comparison.png" alt="erp comparison" width="800"/>


### Sample Output
```
Statistical Results at Electrode Pz
══════════════════════════════════════════════════════════
N400 Component (300-500 ms):
  Congruent: M = -2.15 µV (SD = 1.82)
  Incongruent: M = -5.43 µV (SD = 2.01)
  t = 8.234, p < .001, Cohen's d = 1.72
```

### Dependencies
```python
mne, numpy, pandas, scipy, matplotlib, seaborn, scikit-learn
```

---

## 🎤 Speech Recording Analysis

**Notebook:** [`Speech_Recording_Analysis.ipynb`](./Notebook/Speech_Recording_Analysis.ipynb)

<img src="https://github.com/chemvatho/XLinCoLab/blob/main/speech_recording_analysis/animated_riverbank_flowing-4.gif" alt="riverbank" width="800"/>

A complete acoustic phonetics pipeline using Praat (via Parselmouth) and librosa for analyzing speech recordings.

### Features
- **F0 Extraction:** Multiple algorithms (Praat autocorrelation, pYIN, CREPE)
- **Formant Analysis:** F1–F4 tracking with bandwidth measurements
- **Voice Quality:** Jitter, shimmer, harmonics-to-noise ratio (HNR)
- **Visualization:** Spectrograms, formant tracks, F1-F2 vowel space plots
- **Batch Processing:** Automated pipeline for multiple audio files

<img src="https://github.com/chemvatho/XLinCoLab/blob/main/speech_recording_analysis/diphthongs.gif" alt="diphthong" width="800"/>


### Sample Output
```
Voice Quality Measures:
══════════════════════════════════════════════════════════
Jitter (local): 0.892%
Shimmer (local): 3.241%
HNR: 18.45 dB

Formant Statistics:
  F1: M = 512 Hz (SD = 89)
  F2: M = 1543 Hz (SD = 234)
  F3: M = 2651 Hz (SD = 187)
```

### Dependencies
```python
parselmouth, librosa, numpy, pandas, scipy, matplotlib, seaborn, soundfile
```

---

## 👁️ Eye-tracking Analysis

**Notebook:** [`Peekbank_Eyetracking_Analysis.ipynb`](https://github.com/chemvatho/Peekbank-Analysis)

Analysis pipeline for visual world paradigm eye-tracking experiments using the Peekbank database framework.

### Features
- **Data Processing:** Fixation extraction, area-of-interest (AOI) mapping
- **Time Course Analysis:** Proportion of looks over time
- **Growth Curve Analysis:** Polynomial and GAM modeling of looking behavior
- **Statistical Analysis:** Cluster-based permutation tests, bootstrapped CIs
- **Visualization:** Time course plots, heatmaps, individual differences

### Repository
See the dedicated repository: [github.com/chemvatho/Peekbank-Analysis](https://github.com/chemvatho/Peekbank-Analysis)

---

## ⏱️ Reaction Time Analysis

**Notebook:** [`Reaction_Time_Analysis.ipynb`](./Notebook/Reaction_Time_Analysis.ipynb)

<img src="https://github.com/chemvatho/XLinCoLab/blob/main/RT-Results/rt_distributions.png" alt="diphthong" width="800"/>

A psycholinguistics-focused pipeline for analyzing reaction time data from lexical decision and similar paradigms.

### Features
- **Preprocessing:** Outlier removal (absolute bounds + SD-based), accuracy filtering
- **Distribution Analysis:** RT histograms, Q-Q plots, log transformation assessment
- **Effect Analysis:** Lexicality, word frequency, semantic priming effects
- **ANOVA:** Repeated measures with pairwise comparisons (Bonferroni correction)
- **Mixed-Effects Models:** Linear mixed models with random slopes for subjects/items
- **Visualization:** Interaction plots, by-subject distributions, effect size plots

<img src="https://github.com/chemvatho/XLinCoLab/blob/main/RT-Results/qq_plots.png" alt="diphthong" width="800"/>


### Sample Output
```
Repeated Measures ANOVA (Frequency × Priming):
══════════════════════════════════════════════════════════════════════
Source          SS        DF       MS         F       p-unc    η²
──────────────────────────────────────────────────────────────────────
frequency    125432.1      1   125432.1   89.234    <.001   0.124
priming       45621.8      1    45621.8   32.451    <.001   0.045
freq*prime     2341.2      1     2341.2    1.665     .207   0.002
```

### Dependencies
```python
pandas, numpy, scipy, statsmodels, pingouin, matplotlib, seaborn
```

---
<img src="https://github.com/chemvatho/XLinCoLab/blob/main/RT-Results/rt_effects.png" alt="diphthong" width="800"/>

..............................
## 🚀 Quick Start
..............................
### Option 1: Google Colab (Recommended)
Click the "Open in Colab" badge on any notebook to run directly in your browser—no installation required.

### Option 2: Local Installation

```bash
# Clone the repository
git clone https://github.com/chemvatho/experimental-linguistics-pipelines.git
cd experimental-linguistics-pipelines

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook
```

### Requirements File
```
# requirements.txt
numpy>=1.21.0
pandas>=1.3.0
scipy>=1.7.0
matplotlib>=3.4.0
seaborn>=0.11.0
statsmodels>=0.13.0
pingouin>=0.5.0
mne>=1.0.0
librosa>=0.9.0
parselmouth>=0.4.0
scikit-learn>=1.0.0
soundfile>=0.10.0
```

---

## 📊 Datasets

These pipelines are designed to work with the following open datasets:

| Data Type | Dataset | Source |
|-----------|---------|--------|
| EEG | EEG Dataset | [Kaggle](https://www.kaggle.com/datasets/samnikolas/eeg-dataset) |
| EEG | ZuCo (reading EEG) | [OSF](https://osf.io/q3zws/) |
| Speech | Speech Accent Archive | [Kaggle](https://www.kaggle.com/datasets/rtatman/speech-accent-archive) |
| Speech | LJSpeech | [Kaggle](https://www.kaggle.com/datasets/mathurinache/the-lj-speech-dataset) |
| Eye-tracking | Peekbank | [peekbank.stanford.edu](https://peekbank.stanford.edu/) |
| Reaction Time | British Lexicon Project | [crr.ugent.be](http://crr.ugent.be/programs-data/lexicon-projects) |
| Reaction Time | MALD Database | [Springer](https://link.springer.com/article/10.3758/s13428-018-1056-1) |

---

## 📁 Repository Structure

```
experimental-linguistics-pipelines/
│
├── README.md                          # This file
├── requirements.txt                   # Python dependencies
├── LICENSE                            # MIT License
│
├── notebooks/
│   ├── EEG_Analysis_Pipeline.ipynb
│   ├── Speech_Recording_Analysis.ipynb
│   └── Reaction_Time_Analysis.ipynb
│
├── data/                              # Sample data (gitignored for large files)
│   └── .gitkeep
│
├── outputs/                           # Analysis outputs
│   ├── figures/
│   └── results/
│
└── utils/                             # Helper functions
    ├── __init__.py
    ├── preprocessing.py
    └── visualization.py
```

---

## 📚 Related Publications

- Chem, V. (in prep.). Adapting forced alignment for Khmer, a low-resource language.
- Chem, V. (in prep.). The Illustration of IPA: Khmer (Phnom Penh Dialect). *Journal of the IPA*.
- Chem, V. (2020). Khmer Vowel System: Structure and Variation. *CJBAR*, 2(2).

---

## 🔗 Related Resources

- **Khmer G2P Tool:** [huggingface.co/spaces/Vatho/Khmer-g2p](https://huggingface.co/spaces/Vatho/Khmer-g2p)
- **Peekbank Analysis:** [github.com/chemvatho/Peekbank-Analysis](https://github.com/chemvatho/Peekbank-Analysis)
- **University Profile:** [ifl.phil-fak.uni-koeln.de/phonetik/personen/vatho-chem-ma](https://ifl.phil-fak.uni-koeln.de/phonetik/personen/vatho-chem-ma)

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **Supervisors:** Prof. Dr. Martine Grice & PD Dr. Constantijn Kaland (University of Cologne)
- **Mentors:** Prof. Dr. Reinhold Greisbach & T. Mark Ellison (University of Cologne)
- **Funding:** KAAD (Katholischer Akademischer Ausländer-Dienst)
- **Tools:** [Praat](https://www.fon.hum.uva.nl/praat/), [MNE-Python](https://mne.tools/), [librosa](https://librosa.org/)

---

## 🙏 AI Assisted tools

The repository was developed with the assistance of Claude (Anthropic), which supported logical reasoning and algorithm design. Its integration with NotebookLM led to the creation of a pilot project, which is documented on GitHub.

<p align="center">
  <i>Developed for the Experimental Service Hub, Data Center for the Humanities (DCH)</i><br>
  <i>University of Cologne, Germany</i>
</p>
