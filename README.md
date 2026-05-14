# PolyApred: Prediction of Polyadenylation Signals in Human DNA Sequences

## Overview

PolyApred is a computational method developed for predicting polyadenylation [poly(A)] signals in human DNA sequences using machine learning and nucleotide frequency analysis.

The method uses:

- Mononucleotide frequencies
- Dinucleotide frequencies
- Trinucleotide frequencies
- Tetranucleotide frequencies
- Split nucleotide frequency strategies
- Hybrid Support Vector Machine (SVM) models

PolyApred was designed to distinguish real poly(A) signals from pseudo-poly(A) signals present in coding regions.

---

# Research Paper

## Title

Prediction of polyadenylation signals in human DNA sequences using nucleotide frequencies

## Authors

- Firoz Ahmed
- Manish Kumar
- Gajendra P. S. Raghava

## Journal

In Silico Biology

## Volume

9

## Article Number

0012

## Published Date

23 May 2009

 DOI

https://doi.org/10.3233/ISB-2009-0428

---

# Background

Polyadenylation is an important biological process involved in:

- mRNA maturation
- mRNA stability
- Nuclear export
- Translation efficiency
- Post-transcriptional regulation

The poly(A) signal determines the cleavage site where the poly(A) tail is added to pre-mRNA.

Mutations in poly(A) signals are associated with several diseases including beta-thalassemia.

The canonical human poly(A) signal is:

- AATAAA

Several other variants also exist in human genes.

---

# Objectives

The study aimed to:

- Predict poly(A) signals in human DNA sequences
- Distinguish real PAS from pseudo-PAS
- Improve prediction accuracy using nucleotide frequencies
- Develop hybrid machine learning models
- Create a user-friendly prediction server

---

# Dataset Information

## Positive Dataset

- 2327 sequences
- Sequence length: 206 nucleotides
- Real poly(A) signals located at the center

## Negative Dataset

- 2333 sequences
- Extracted from coding regions
- Contained pseudo-PAS motifs at the center

---

# Independent Dataset

The independent dataset contained:

- 982 positive sequences
- Four different negative datasets:
  - Coding regions
  - Introns
  - Shuffled sequences
  - Markov model generated sequences

---

# Feature Representation

## Binary Pattern

Each nucleotide was encoded using binary vectors:

- A = [1,0,0,0]
- C = [0,1,0,0]
- G = [0,0,1,0]
- T = [0,0,0,1]

---

# Nucleotide Frequency Features

The following frequency-based features were calculated:

- Mononucleotide frequencies
- Dinucleotide frequencies
- Trinucleotide frequencies
- Tetranucleotide frequencies

For:

- 100 nt upstream region
- 100 nt downstream region

---

# Split Nucleotide Frequency

The upstream and downstream regions were divided into smaller regions:

## Upstream

- UP51_100
- UP1_50

## Downstream

- DW1_50
- DW51_100

This region-specific strategy improved prediction performance.

---

# Second Order Dinucleotide Frequency

The model also considered relationships between:

- First nucleotide
- Third nucleotide

instead of only adjacent nucleotides.

---

# Machine Learning Technique

The models were developed using:

- Support Vector Machine (SVM)
- SVM_light package
- Radial Basis Function (RBF) kernel

---

# Sequence Analysis Findings

The study observed:

- T nucleotide frequency was higher in real PAS sequences
- TT and TG dinucleotides were enriched near PAS regions
- Region DW1_50 contained highly informative motifs
- Region-specific nucleotide distributions improve PAS prediction

---

# Performance of Models

## Simple Frequency Models

| Feature Type | MCC |
|---|---|
| Mononucleotide | 0.51 |
| Dinucleotide | 0.62 |
| Trinucleotide | 0.67 |
| Tetranucleotide | 0.68 |

---

# Split Frequency Models

| Feature Type | MCC |
|---|---|
| Mononucleotide | 0.58 |
| Dinucleotide | 0.69 |
| Trinucleotide | 0.70 |
| Tetranucleotide | 0.69 |

---

# Best Hybrid Model

The final hybrid model combined:

- Dinucleotide frequency
- Second-order dinucleotide frequency
- Tetranucleotide frequency

## Performance

| Metric | Value |
|---|---|
| Accuracy | 85.75% |
| Sensitivity | 82.17% |
| Specificity | 89.34% |
| MCC | 0.72 |

---

# Independent Dataset Performance

The hybrid model achieved:

| Dataset Type | Precision |
|---|---|
| Coding Sequences | 89.7% |
| Introns | 78.8% |
| Shuffled Sequences | 95.7% |
| Markov Sequences | 75.8% |

Sensitivity:

- 57%

---

# Prediction of PAS Variants

The method successfully predicted 13 different PAS variants including:

- AATAAA
- ATTAAA
- TATAAA
- AGTAAA
- AAGAAA
- AATATA
- AATACA
- CATAAA
- GATAAA
- AATGAA
- TTTAAA
- ACTAAA
- AATAGA

Overall sensitivity:

- 79.38%

---

# Web Server Features

PolyApred allows users to:

- Upload FASTA sequences
- Predict poly(A) signals
- Adjust prediction thresholds
- Detect known PAS signatures
- Identify putative novel PAS signals

The server categorizes predictions into:

1. Canonical PAS signals
2. Known PAS variants
3. Novel predicted PAS signals

Web Server:

http://www.imtech.res.in/raghava/polyapred/

---

# Applications

PolyApred can be used for:

- Genome annotation
- Gene boundary identification
- 3'-UTR analysis
- Alternative polyadenylation research
- Transcriptomics
- Post-transcriptional regulation studies

---

# Technologies Used

- Support Vector Machine (SVM)
- RBF Kernel
- Nucleotide Frequency Analysis
- Machine Learning
- Statistical Analysis
- ROC Analysis

---

# Important Findings

The study demonstrated that:

- Frequency-based approaches outperform position-specific approaches
- Split nucleotide frequency significantly improves prediction accuracy
- Hybrid feature integration improves PAS prediction
- Region-specific nucleotide composition is highly informative

---

# Conclusion

PolyApred provides a highly effective computational framework for predicting polyadenylation signals in human DNA sequences.

The hybrid SVM-based approach achieved superior performance compared with previously available methods and provides a useful resource for genome annotation and post-transcriptional regulation studies.

---

# Contact

## Dr. G. P. S. Raghava

Email: raghava@iiitd.ac.in

Address:  
Indraprastha Institute of Information Technology Delhi

---

# License

This project is intended for academic and research purposes only.
