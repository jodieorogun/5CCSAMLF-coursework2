# 5CCSAMLF-coursework2

This repository contains the code for **5CCSAMLF Coursework 2**, based on the paper:

**Hacohen et al. (2022), _Active Learning on a Budget: Opposite Strategies Suit High and Low Budgets_**

The coursework tasks were:
1. Implement the TPCRP / TypiClust-style active learning method on **CIFAR-10**
2. Write a report summarising and evaluating the paper
3. Propose and test a modification to the original method

---

## Project Overview

This project studies **low-budget active learning**, where only a very small number of samples are labelled. The paper argues that in this setting, standard uncertainty-based methods often perform poorly, and that it is better to select **representative and typical** examples from the data distribution.

The implementation in this repository evaluates TPCRP and several baselines under multiple frameworks:

- **Framework 1:** fully supervised training on the queried labelled subset
- **Framework 2:** embedding-based evaluation using a trained ResNet-18 feature extractor and a linear classifier
- **Framework 3:** simplified semi-supervised approximation inspired by the paper’s FlexMatch framework

Implemented methods:
- **TPCRP**
- **Random**
- **Margin**
- **Entropy**
- **TPCRP-Entropy** (proposed modification)

---

## Repository Structure

```text
.
├── tpcrp.ipynb
├── README.md
├── tpcrp_report.pdf
├── test_embeddings.pt
├── test_labels.pt
├── framework1Plot.png
├── framework2Plot.png
├── framework3Plot.png
├── frameworkResults.csv
├── framework2UpdatedResults.csv
└── tpcrpAcrossFrameworks.png

```
## Requirements

The project was developed in Python using the following main packages:

- Python 3.10
- PyTorch
- torchvision
- scikit-learn
- pandas
- matplotlib
- jupyter

### Conda setup

Create and activate an environment:

```bash
conda create -n tpcrp python=3.10
conda activate tpcrp
conda install pytorch torchvision -c pytorch
conda install scikit-learn pandas matplotlib jupyter
```
