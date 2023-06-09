# Breast tumor detection and diagnostic on ultrasound
Project 3A HSB DL

Authors : Céline Carré, Alice Simon and Lucie Engel 

## Context

Although in France mammogram is the reference examination for the breast cancer screening program, ultrasound can be performed as well for women with dense breasts or to better analyse a breast tumor detected on the mammogram. 

## Dataset

The data collected include breast ultrasound images among women in ages between 25 and 75 years old. This data was collected in 2018. The number of patients is 600 female patients. The dataset consists of 780 images with an average image size of 500*500 pixels. The images are in PNG format. The ground truth segmentation masks are presented for each ultrasound image. The images are categorized into three classes, which are normal, benign, and malignant.
You can download the dataset here : 
https://www.kaggle.com/datasets/aryashah2k/breast-ultrasound-images-dataset

## Model 

Our goal is to predict both the segmentation mask and the class of the exam (normal, benign tumor, malignant tumor). We combine two tasks : a segmentation task and a classification task. 
We investigated two approaches : 
* a sequential approach : a UNet model and after a ResNet50
* a hybrid model : a UNet model with a classification head on top of the features of the encoder. 

## Code

Two collab notebooks are available in the repository, one for each approach. Models were saved as state-dicts. Note that you might need to change paths in the code to make it work in your drive. Our folder is organised in the following way : 

```
├── Projet_DL
 └── state_dict
   └── hybride
   └── label_only
   └── mask_only
 └── Dataset_BUSI_with_GT
```
## Results

Results are presented in the pdf presentation : Breats cancer detection on ultrasound.pdf. The model state-dicts can be found in the tag section for each model. 

## Conclusion

In conclusion, we obtain good results for this school project. If we had more time, we would investigate the following ideas : 
* correct the dataset imbalance 
* evaluate our models' performances on a independant test set (another country, another echograph, another clinical center)
* use weights in the loss : false negatives must be prevented at all cost.

This algorithm could be used as a training tools for medical interns, or as a safety net for trained radiologists. It could also be integrated to a portable ultrasound probe for medical deserts or countries with poor medical coverage.

## References 

* Al-Dhabyani W, Gomaa M, Khaled H, Fahmy A. Dataset of breast ultrasound images. Data in Brief. 2020 Feb;28:104863. DOI: 10.1016/j.dib.2019.104863.
* Pytorch documentation
