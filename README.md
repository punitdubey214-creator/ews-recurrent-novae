# Early Warning Signals in Recurrent Novae

## Overview

This repository contains the analysis, simulations, and toy models developed to investigate the emergence of **Early Warning Signals (EWS)** in recurrent novae.

The project was motivated by an intriguing observational result: while the recurrent nova **T Coronae Borealis (T CrB)** exhibits clear signatures of Early Warning Signals prior to eruption, **RS Ophiuchi (RS Oph)** does not show similarly robust behavior. The goal of this work is to identify the physical mechanism responsible for this difference.

The study combines observational light-curve analysis, Recurrence Quantification Analysis (RQA), and physically motivated accretion-rate toy models inspired by MESA simulations.

---

## Scientific Motivation

Many complex dynamical systems exhibit characteristic statistical signatures before undergoing a critical transition. These signatures, known as **Early Warning Signals (EWS)**, arise from a phenomenon called **Critical Slowing Down (CSD)**.

EWS have been successfully detected in systems ranging from ecology and climate science to stellar astrophysics. In particular, previous work demonstrated EWS preceding the Great Dimming of Betelgeuse.

This project investigates whether similar signatures can be detected before recurrent nova eruptions.

---

## Main Results

### T CrB

Analysis of the T CrB light curve reveals consistent increasing trends in:

* Variance
* Lag-1 Autocorrelation (ACF(1))
* Detrended Fluctuation Analysis (DFA)
* Determinism (DET)
* Laminarity (LAM)

These trends are characteristic signatures of Critical Slowing Down and suggest that the system approaches a critical transition before eruption.

### RS Oph

The same methodology was applied to multiple RS Oph eruption cycles.

Unlike T CrB, RS Oph generally does not exhibit robust and consistent EWS signatures across its observed outbursts.

This discrepancy motivated the development of a series of theoretical toy models.

---

## Research Evolution

### Phase 1: Observational Analysis

The initial study focused on applying EWS techniques to observational light curves from:

* T CrB
* RS Oph

Key result:

```text
T CrB  → Strong EWS detected
RS Oph → Weak or absent EWS
```

---

### Phase 2: Accretion Disk Hypothesis

The first hypothesis proposed that:

* T CrB contains a stable long-lived accretion disk capable of approaching a critical state gradually.
* RS Oph contains a short-lived unstable disk that transitions too rapidly to produce EWS.

Subsequent literature review suggested that this explanation was insufficient because both systems may experience disk instabilities.

---

### Phase 3: Toy Models

To isolate the underlying physics, simplified accretion-driven models were developed.

These models explored:

* Slowly varying accretion rates
* Stochastic forcing
* Thermal instability
* Disc-instability inspired behavior
* Sudden versus gradual transitions

---

### Phase 4: Slowly Driven Systems

The toy models demonstrated that:

* Slowly evolving control parameters generate robust EWS.
* Rapid transitions generally suppress EWS.
* EWS emerge before the onset of instability rather than during the outburst itself.

This result supports the theoretical expectation that Critical Slowing Down requires a gradual loss of stability.

---

### Phase 5: Timescale Study

A parameter study was performed by varying the timescale over which the accretion rate evolves.

The results indicate:

* Short timescales produce little or no EWS.
* Long-timescale evolution generates increasingly strong EWS.
* Significant EWS appear when the accretion-rate evolution occurs on timescales of approximately **15–18 years**.

This behavior is qualitatively consistent with observations of T CrB and supports the idea that long-duration enhanced mass transfer may be responsible for the observed EWS.

---

## Methods

### Early Warning Signal Indicators

The following indicators are computed using rolling-window analysis:

* Variance
* Lag-1 Autocorrelation (ACF(1))
* Detrended Fluctuation Analysis (DFA)
* Determinism (DET)
* Laminarity (LAM)

### Trend Detection

Trends are quantified using:

* Kendall's Tau
* Modified Mann-Kendall Test (Hamed-Rao correction)

### Recurrence Quantification Analysis

RQA metrics are computed from recurrence plots:

* DET (Determinism)
* LAM (Laminarity)

These measures provide information about evolving dynamical structure in the system.

---

## Repository Structure

```text
data/
│
├── TCrB/
│   ├── lightcurve.csv
│   └── processed_data.csv
│
├── RSOph/
│   ├── lightcurve.csv
│   └── processed_data.csv
│
notebooks/
│
├── 01_TCrB_EWS.ipynb
├── 02_RSOph_EWS.ipynb
├── 03_MESA_Toy_Model.ipynb
├── 04_Disc_Instability_Model.ipynb
└── 05_Gaussian_Accretion_Model.ipynb
│
src/
│
├── ews.py
├── rqa.py
├── detrending.py
└── statistics.py
│
results/
│
├── figures/
└── tables/
│
docs/
│
└── project_story.md
│
README.md
```

---

## Workflow

```text
Observational Light Curves
           │
           ▼
     EWS Analysis
           │
           ▼
  T CrB shows EWS
  RS Oph does not
           │
           ▼
    Physical Question
           │
           ▼
     Toy Models
           │
           ▼
 Slowly Driven Systems
           │
           ▼
 EWS appear before instability
           │
           ▼
 Timescale Study
           │
           ▼
 ~15–18 year evolution
 produces robust EWS
```

---

## Software and Libraries

This project makes use of:

* Python
* NumPy
* Pandas
* SciPy
* Matplotlib
* Statsmodels
* PyRQA
* scikit-learn
* MESA outputs

---

## Future Work

Several questions remain open:

* Why does T CrB exhibit stronger EWS than RS Oph?
* What physical mechanism controls long-term mass-transfer variations?
* Can realistic binary-evolution models reproduce the observed timescales?
* Can EWS be used as predictive tools for future recurrent nova eruptions?
* Can these methods be applied to other cataclysmic variables and accreting compact objects?

---

## Author

**Punit Dubey**

National Institute of Technology Rourkela

Email: [punitdubey214@gmail.com](mailto:punitdubey214@gmail.com)

---

## Acknowledgements

This work was carried out under the guidance of:

* Dr. Deepika Bollimpalli
* Dr. Sneha Kachhara

The project was inspired by previous work on Early Warning Signals in Betelgeuse and by ongoing efforts to understand critical transitions in astrophysical systems.

---

## Citation

If you use this repository in your research, please cite:

```bibtex
@misc{dubey2026ews,
  author       = {Punit Dubey},
  title        = {Early Warning Signals in Recurrent Novae},
  year         = {2026},
  publisher    = {GitHub},
  journal      = {GitHub Repository},
  url          = {https://github.com/YOUR_USERNAME/ews-recurrent-novae}
}
```

### Related References

```bibtex
@article{George2020Betelgeuse,
  author  = {George, S. V. and Kachhara, S. and Misra, R. and Ambika, G.},
  title   = {Early warning signals indicate a critical transition in Betelgeuse},
  journal = {Astronomy & Astrophysics},
  volume  = {640},
  pages   = {L21},
  year    = {2020}
}

@article{Scheffer2009EWS,
  author  = {Scheffer, M. and Bascompte, J. and Brock, W. A. and others},
  title   = {Early-warning signals for critical transitions},
  journal = {Nature},
  volume  = {461},
  pages   = {53--59},
  year    = {2009}
}
```

---

## License

This repository is released under the MIT License.

Feel free to use, modify, and distribute the code with appropriate attribution.
