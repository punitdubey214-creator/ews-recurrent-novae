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

### For both, we studied different window sizes and the de-trending parameter. The results are consistent. 

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

* T CrB contains a stable, long-lived accretion disk capable of approaching a critical state gradually.
* RS Oph contains a short-lived unstable disk that transitions too rapidly to produce EWS.

A subsequent literature review suggested that this explanation was insufficient because both systems may experience disk instability.

---

### Phase 3: Toy Models

To isolate the underlying physics, simplified accretion-driven models were developed. This Toy model comes from MESA Simulation. We change the accretion rate with time for a 1.02 solar mass White dwarf. More details on this implementation can be found in a different repository of mine. ( https://github.com/punitdubey214-creator/MESA_time_dependent_accretion )

These models explored:

* Slowly varying accretion rates
* Stochastic forcing
* Thermal instability
* Disc-instability-inspired behaviour
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

This behaviour is qualitatively consistent with observations of T CrB and supports the idea that long-duration enhanced mass transfer may be responsible for the observed EWS.

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
├── TCrB's data can be downloaded from the AAVSO light curve data set.
├── RSoph.txt ( also comes from AAVSO lightcurve ) 
notebooks/
│
├── 01_Lightcurve_analysis.ipynb 
├── 02_MESA_Toy_Models_and_time_scale_study.ipynb
│
│
results/
│
├── figures/
└── tables/
│
docs/
│
└── project_v01.pdf
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
{ Sin function in accretion rate,
 Linearly decreasing accretion rate
(with and without noise ),
 Disc instability model }
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
Also, we acknowledge the AAVSO lightcurve data set for providing the data for this research. 

---
## References

1. Scheffer, M., Bascompte, J., Brock, W. A., Brovkin, V., Carpenter, S. R., Dakos, V., Held, H., van Nes, E. H., Rietkerk, M., & Sugihara, G. (2009). *Early-warning signals for critical transitions*. Nature, **461**, 53–59.

2. George, S. V., Kachhara, S., Misra, R., & Ambika, G. (2020). *Early warning signals indicate a critical transition in Betelgeuse*. Astronomy & Astrophysics, **640**, L21.

3. Bury, T., Sujith, R. I., Scheffer, M., Lenton, T. M., & Anand, M. (2021). *Detecting and distinguishing tipping points using spectral early warning signals*. Journal of the Royal Society Interface, **18**, 20200482.

4. Bollimpalli, D. A., Hameury, J.-M., & Lasota, J.-P. (2018). *Disc instabilities and nova eruptions in symbiotic systems: RS Ophiuchi and Z Andromedae*. Monthly Notices of the Royal Astronomical Society, **481**, 5422–5438.

5. Alexander, R. D., Wynn, G. A., King, A. R., & Pringle, J. E. (2011). *Disc instability in RS Ophiuchi: a path to Type Ia supernovae?* Monthly Notices of the Royal Astronomical Society, **418**, 2576–2587.

6. Zamanov, R. K., Stoyanov, K. A., Marchev, V., Minev, M., Marchev, D., Moyseev, M., Marti, J., Bode, M. F., Konstantinova-Antova, R., & Stefanov, S. (2024). *Size of the accretion disc in the recurrent nova T CrB*. Astronomische Nachrichten, 345, e20240031.

7. Zamanov, R., Boeva, S., Latev, G. Y., Semkov, E., Minev, M., Kostov, A., Bode, M. F., Marchev, V., & Marchev, D. (2024). *Accretion in the recurrent nova T CrB: Linking the superactive state to the predicted outburst*. Astronomy & Astrophysics, **685**, A167.

8. Planquart, L., Jorissen, A., & Van Winckel, H. (2025). *Resolving the mass transfer in the symbiotic recurrent nova T Coronae Borealis*. Astronomy & Astrophysics.


---

### Data Sources

* American Association of Variable Star Observers (AAVSO)
* MESA (Modules for Experiments in Stellar Astrophysics)
* T CrB and RS Oph observational light-curve archives
* Recurrence Quantification Analysis (RQA) framework

---


## License

This repository is released under the MIT License.

Feel free to use, modify, and distribute the code with appropriate attribution.
