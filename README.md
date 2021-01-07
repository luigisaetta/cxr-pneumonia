## CXR-Pneumonia Detection

This repository contains all my work done on the **NIH-Chest X-Rays 14 (2017)** Dataset for Pneumonia Detection

### List of files 

| File name     | Description                     |Link.                                                              |
| ------------- |---------------------------------|-------------------------------------------------------------------|
| EDA     | EDA on full dataset (112120 imgs) and on train and test set| https://github.com/luigisaetta/cxr-pneumonia/blob/main/EDA.ipynb  |
| Intensity Profiles | Analysis of Intensity Profiles with plots | https://github.com/luigisaetta/cxr-pneumonia/blob/main/Intensity%20Profiles.ipynb |
| prepare_dataset | code to create train and test datasets with production of TFRecord files | https://github.com/luigisaetta/cxr-pneumonia/blob/main/prepare_dataset.ipynb | 
| build-and-train-on-tpu | Build and training of the model (on Kaggle TPU), with production of statistics per thresholds and F1-score plot | https://github.com/luigisaetta/cxr-pneumonia/blob/main/build-and-train-on-tpu.ipynb |

### Features:
* Train and Test datasets have been prepared compressing original images (PNG 1024x1024) in JPEG 512x512 and packing all in **TensorFlow TFRecord** files
* TFRecord files published in **Kaggle Dataset**: https://www.kaggle.com/luigisaetta/nih-cxr-pneu512
* Training on **TPU** (Kaggle)
* For training, it is adopted **K-fold Cross Validation** (K=5)
* Learning Rate SCheduler to control variation of Learning Rate during epochs
* 5 models are produces building an **Ensemble**: predictions are average from prediction from each single model
* code for controls and inference on **DICOM** files

                                                                  
### Updates
Last update: 07/01/2021
* new version, using images resized to 512x512
* new code for train/test split


