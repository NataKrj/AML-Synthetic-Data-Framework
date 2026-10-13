# AML Synthetic Data Framework

A scenario-based framework for synthetic transaction data generation and model evaluation in anti-money laundering transaction monitoring.

This repository contains the source code and experimental artefacts developed as part of the master's thesis **"Automated Risk-Scoring System for Financial Institutions"** and the related publication **"Synthetic Data for Anti-Money Laundering Transaction Monitoring and Model Evaluation"**, presented at RelStat 2026.

The framework covers scenario-based synthetic transaction generation, data-quality checks, class-imbalance handling, machine-learning model selection, training and retraining, and binary and scenario-level model evaluation.

Its purpose is to provide a controlled environment for AML model testing and comparison without using sensitive customer transaction data.

## 1. Overview

The pipeline follows these main stages (see thesis diagram):

1. Choosing a data synthesis method  
2. Building a scenario catalogue (FI guidelines, EU directives)  
3. Synthetic transaction generation  
4. Data-quality check
5. Model selection (AutoML and expert shortlisting)
6. Class-imbalance handling (SMOTE / ADASYN / ROSE)  
7. Training / retraining mode and threshold update  
8. Adaptivity check  

This repository provides code, sample configs and notebooks for each stage.

## 2. Repository structure
```
/1_data_synthesis/          # code for synthetic transaction generation (rule-based + generative tests), configs/specs
/2_scenario_catalogue/      # scenario catalogue and scenario combinations (stored as design artefacts, incl. Excel)
/3_data_quality/            # notebooks for rule-based data validation and basic profiling checks
/4_model_selection/         # model selection experiments (candidate comparison, feature importance, shortlist)
/5_class_balance/           # imbalance handling experiments (SMOTE/ADASYN/ROSE and baseline strategies)
/6_training_mode/           # training experiments + outputs:
                            # - binary baseline on two datasets (Syn100 vs Syn500), incremental learning vs full retraining,
                            # - binary with OOF + Platt scaling, incl. full retraining (small vs large),
                            # - multiclass baseline runs (Syn100 vs Syn500)
/meeting minutes/           # meeting and correspondence summary
/artefacts/                 # supporting materials (slides, plan/Gantt snapshots, conference materials, Zotero library)
```
### Synthetic datasets
- **Syn100:** 10,000 normal and 100 suspicious transactions.
- **Syn500:** 50,000 normal and 500 suspicious transactions.

Scenario definitions and scenario combinations used for generation are available in
/2_scenario_catalogue/. Each dataset group is organised into five consecutive data
packages (B1–B5), and all training stages are executed separately for Syn100 and Syn500.

## Project plan and evidence
GitHub Projects is used to document the completed research and implementation stages:
- Table view: https://github.com/users/NataKrj/projects/4/views/1
- Board view: https://github.com/users/NataKrj/projects/4/views/2
- Roadmap view: https://github.com/users/NataKrj/projects/4/views/3

## Additional experimental materials
Extended experimental results are available here:
- https://drive.google.com/file/d/1NRxHzGbsFfVxNoBQbD-i_ErHGbw8SaiA/view?usp=sharing (7z archive)
- https://drive.google.com/file/d/1dZ8euOKW4qUbmQcJeBttahok9126V6uo/view?usp=sharing (zip archive)
