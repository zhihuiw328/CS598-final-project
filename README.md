# Benchmarking Deep Learning Architectures for Predicting Readmission to the ICU and Describing Patients-at-Risk

This repository is the official implementation of Benchmarking Deep Learning Architectures for Predicting Readmission to the ICU and Describing Patients-at-Risk (https://www.nature.com/articles/s41598-020-58053-z#Sec13). 

## Requirements

To install requirements:

```setup
pip install -r requirements.txt
```

We require the MIMIC-III dataset, which can be obtained here: https://physionet.org/content/mimiciii/1

This dataset requires credentialed access, so if you choose not to use the dataset, you can instead use the pretrained models.

## Training

To train the model(s) in the paper, run the cells below the model section. This will train the model, which is the 
bidirectional recurrent neural network with time decay and an attention mechanism, as well as the training of the 
ablation study.

The appropriate hyperparameters, as well as training procedure are all outlined in this section. Hyperparams: learning_rate = 0.001 batch_size = 128 num_epochs = 80 dropout_rate = 0.5

## Evaluation

The evaluation of the models are done in the Results section. This includes both the evaluation of the original model, as well as
the model with ablations. The metrics that we have chosen to evaluate are the following, Average Precision: proportion of positive 
predictions that are actually correct, AUROC: the area under the ROC curve, F1 score: measure of predictive performance, 
Sensitivity: the proportion of actual positive that was identified incorrectly, Specificity: proportion of true negatives 
that were identified by the model, Time: the average epoch time for training of the model.

## Pre-trained Models

You can download pretrained models here:

https://github.com/sebbarb/time_aware_attention


## Results

Our models achieves the following performance on :


| Model name                   | Average Precision | AUROC  | F1 Score | Sensitivity | Specificity |
| ---------------------------- | ----------------- | ------ | -------- | ----------- | ----------- |
| BIRNN_Time_Decay_Attention   |     0.2965        | 0.7028 |  0.3398  |   0.6755    |   0.6443    |
| BIRNN_Time_Decay             |     0.2854        | 0.7028 |  0.3295  |   0.7282    |   0.5893    |

