## CXR-Pneumonia Detection

This repository contains all my work done on the **NIH-Chest X-Rays 14 (2017)** Dataset for Pneumonia Detection

![GRAD-Cam](/images/grad-cam.png)

### List of files 

| File name     | Description                     |Link.                                                              |
| ------------- |---------------------------------|-------------------------------------------------------------------|
| EDA     | EDA on full dataset (112120 imgs) | [EDA.ipynb](EDA.ipynb)  |
| EDA-train-test | EDA only on data selected for train and test | [EDA-train-test.ipynb](EDA-train-test.ipynb) |
| Intensity Profiles | Analysis of Intensity Profiles with plots | [Intensity Profiles.ipynb](Intensity%20Profiles.ipynb) |
| prepare_dataset | code to select images for train and test datasets with production of TFRecord files | [prepare_dataset.ipynb](prepare_dataset.ipynb) | 
| build-and-train-on-tpu | Build and training of the model (on Kaggle TPU), with production of statistics (SENS, SPEC...) per thresholds and F1-score plot | https://github.com/luigisaetta/cxr-pneumonia/blob/main/build-and-train-on-tpu.ipynb |
| InferenceDCM | Load a set of DCM images, makes some check, apply model and predict | https://github.com/luigisaetta/cxr-pneumonia/blob/main/InferenceDCM.ipynb |
| Inference-tests | Predictions on all the images in the test set. Compute metrics (Sens, Spec, Precision, F1score) for different thresholds; Plot Precision vs Recall and F1-score vs thresholds | https://github.com/luigisaetta/cxr-pneumonia/blob/main/Inference-tests.ipynb |
| SaveLoadModels | Code to save architecture of the models in JSON format and to load models | https://github.com/luigisaetta/cxr-pneumonia/blob/main/SaveLoadModels.ipynb |
| AnalyzeStats | Code and plot to analyze F1-score as function of threshold | https://github.com/luigisaetta/cxr-pneumonia/blob/main/AnalyzeStats.ipynb| 

### Features:
* Train and Test datasets have been prepared compressing original images (PNG 1024x1024) in JPEG 512x512 and packing all in **TensorFlow TFRecord** files
* Train set is balanced (50% pneumonia), test set has a 25% of pneumonia
* TFRecord files published in **Kaggle Dataset**: https://www.kaggle.com/luigisaetta/nih-cxr-pneu512
* Training on **TPU** (Kaggle)
* Using Google **EfficientNet B4** 
* For training, it is adopted **K-fold Cross Validation** (K=5)
* **Learning Rate Scheduler** to control variation of Learning Rate during epochs
* **Ensemble** of K=5 models: predictions are average from prediction from each single model
* Code for controls and inference on **DICOM** files
* Plot of Images Intensity profiles for different diseases
* Model interpretation with GRAD-Cam
* Compute best threshold, based on F1-score

### Original FULL dataset
The FULL NIH CXR-17 Dataset can be obtained from https://www.kaggle.com/nih-chest-xrays/data
                                                                  
### Updates
Last update: 07/01/2021
* new version, using images resized to 512x512
* new code for train/test split


