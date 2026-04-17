[![DOI](https://img.shields.io/badge/DOI-10.82901%2Fnemar.nm000143-blue)](https://doi.org/10.82901/nemar.nm000143)

# BNCI2003_IVa Motor Imagery dataset

BNCI2003_IVa Motor Imagery dataset.

## Dataset Overview

- **Code**: BNCI2003-004
- **Paradigm**: imagery
- **DOI**: 10.1109/TBME.2004.827088
- **Subjects**: 5
- **Sessions per subject**: 1
- **Events**: right_hand=0, feet=1
- **Trial interval**: [0, 3.5] s
- **File format**: mat
- **Data preprocessed**: True

## Acquisition

- **Sampling rate**: 100.0 Hz
- **Number of channels**: 118
- **Channel types**: eeg=118
- **Channel names**: AF3, AF4, AF7, AF8, AFp1, AFp2, C1, C2, C3, C4, C5, C6, CCP1, CCP2, CCP3, CCP4, CCP5, CCP6, CCP7, CCP8, CFC1, CFC2, CFC3, CFC4, CFC5, CFC6, CFC7, CFC8, CP1, CP2, CP3, CP4, CP5, CP6, CPz, Cz, F1, F2, F3, F4, F5, F6, F7, F8, FAF1, FAF2, FAF5, FAF6, FC1, FC2, FC3, FC4, FC5, FC6, FCz, FFC1, FFC2, FFC3, FFC4, FFC5, FFC6, FFC7, FFC8, FT10, FT7, FT8, FT9, Fp1, Fp2, Fpz, Fz, I1, I2, O1, O2, OI1, OI2, OPO1, OPO2, Oz, P1, P10, P2, P3, P4, P5, P6, P7, P8, P9, PCP1, PCP2, PCP3, PCP4, PCP5, PCP6, PCP7, PCP8, PO1, PO2, PO3, PO4, PO7, PO8, POz, PPO1, PPO2, PPO5, PPO6, PPO7, PPO8, Pz, T7, T8, TP10, TP7, TP8, TP9
- **Montage**: standard_1005
- **Hardware**: BrainAmp
- **Sensor type**: EEG
- **Line frequency**: 50.0 Hz
- **Online filters**: {'bandpass': [0.05, 200]}

## Participants

- **Number of subjects**: 5
- **Health status**: healthy

## Experimental Protocol

- **Paradigm**: imagery
- **Number of classes**: 2
- **Class labels**: right_hand, feet
- **Trial duration**: 3.5 s
- **Stimulus type**: visual cue
- **Mode**: offline
- **Instructions**: subjects performed motor imagery (left hand, right hand, or right foot) according to visual cue for 3.5 seconds
- **Stimulus presentation**: duration=3.5 s, interval=1.75-2.25 s random, modality=visual

## HED Event Annotations

Schema: HED 8.4.0 | Browse: https://www.hedtags.org/hed-schema-browser

```
  right_hand
    ├─ Sensory-event, Experimental-stimulus, Visual-presentation
    └─ Agent-action
       └─ Imagine
          ├─ Move
          └─ Right, Hand

  feet
    ├─ Sensory-event, Experimental-stimulus, Visual-presentation
    └─ Agent-action
       └─ Imagine, Move, Foot

```
## Paradigm-Specific Parameters

- **Detected paradigm**: motor_imagery
- **Imagery tasks**: right_hand, feet
- **Cue duration**: 3.5 s

## Data Structure

- **Trials**: 280
- **Trials context**: 280 cues per subject, split into labeled training and unlabeled test sets (varying per subject)

## Preprocessing

- **Data state**: downsampled to 100 Hz for offline analysis
- **Preprocessing applied**: True
- **Steps**: bandpass filtering, downsampling
- **Bandpass filter**: {'low_cutoff_hz': 0.05, 'high_cutoff_hz': 200.0}
- **Downsampled to**: 100 Hz
- **Notes**: Band-pass filtered 0.05-200 Hz during acquisition at 1000 Hz with 16-bit (0.1 uV) accuracy, then downsampled to 100 Hz by picking each 10th sample. Original experiment also recorded EMG and EOG but these are not in the shared data files.

## Signal Processing

- **Classifiers**: LDA, regularized LDA
- **Feature extraction**: CSP, SUB (MRP/slow potentials), AR
- **Frequency bands**: alpha=[8, 13] Hz; beta=[15, 25] Hz; alpha_beta=[7, 30] Hz
- **Spatial filters**: CSP, spatial Laplacian

## Cross-Validation

- **Method**: 10x10-fold cross validation
- **Folds**: 10
- **Evaluation type**: within-subject

## BCI Application

- **Applications**: motor_control
- **Environment**: laboratory
- **Online feedback**: False

## Tags

- **Pathology**: Healthy
- **Modality**: Motor
- **Type**: Research

## Documentation

- **DOI**: 10.1109/TBME.2004.827088
- **License**: CC-BY-4.0
- **Investigators**: Guido Dornhege, Benjamin Blankertz, Gabriel Curio, Klaus-Robert Müller
- **Senior author**: Klaus-Robert Müller
- **Contact**: benjamin.blankertz@tu-berlin.de
- **Institution**: Fraunhofer FIRST (IDA); Charité University Medicine Berlin
- **Department**: Fraunhofer FIRST (IDA); Department of Neurology, Campus Benjamin Franklin
- **Address**: 12489 Berlin, Germany; 12203 Berlin, Germany
- **Country**: DE
- **Repository**: BBCI
- **Publication year**: 2004
- **Funding**: Bundesministerium für Bildung und Forschung (BMBF) under Grants FKZ 01IBB02A and FKZ 01IBB02B
- **Keywords**: brain-computer interface, BCI, common spatial patterns, electroencephalogram, EEG, event-related desynchronization, feature combination, movement related potential, multiclass, single-trial analysis

## References

Guido Dornhege, Benjamin Blankertz, Gabriel Curio, and Klaus-Robert Muller. Boosting bit rates in non-invasive EEG single-trial classifications by feature combination and multi-class paradigms. IEEE Trans. Biomed. Eng., 51(6):993-1002, June 2004.

Notes

.. versionadded:: 0.4.0

This is one of the earliest and most influential motor imagery BCI datasets, used extensively for benchmarking classification algorithms. The dataset was part of BCI Competition III and has been cited in hundreds of papers.

See Also

BNCI2014_001 : BCI Competition IV 4-class motor imagery dataset BNCI2014_004 : BCI Competition 2008 2-class motor imagery dataset
Appelhoff, S., Sanderson, M., Brooks, T., Vliet, M., Quentin, R., Holdgraf, C., Chaumon, M., Mikulan, E., Tavabi, K., Hochenberger, R., Welke, D., Brunner, C., Rockhill, A., Larson, E., Gramfort, A. and Jas, M. (2019). MNE-BIDS: Organizing electrophysiological data into the BIDS format and facilitating their analysis. Journal of Open Source Software 4: (1896). https://doi.org/10.21105/joss.01896

Pernet, C. R., Appelhoff, S., Gorgolewski, K. J., Flandin, G., Phillips, C., Delorme, A., Oostenveld, R. (2019). EEG-BIDS, an extension to the brain imaging data structure for electroencephalography. Scientific Data, 6, 103. https://doi.org/10.1038/s41597-019-0104-8

---
Generated by MOABB 1.5.0 (Mother of All BCI Benchmarks)
https://github.com/NeuroTechX/moabb
