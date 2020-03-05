# Histopathological cancer detection in whole slide images

## Code Challenge Resubmission GSOC-2020 - Cancer Region of interest Extraction and Machine learning

> This repo contains resubmission for code challenge by caMicroscope.

![](https://github.com/divyaprabha123/caMicroscopeGSOC_2/blob/master/output/FINAL.gif)


## Code challenge

One to two paragraph statement about your product and what it does.

## Approach

 - Whole slide images are first split into patches (smaller region) of size 512 * 512 with stride as 96, then each of this patches is fed into trained **Mnasnet** (Platform-Aware Neural Architecture Search for Mobile) model.
 - Mnasnet then classifies all the patches in the WSI into two classes. A positive label indicates that there is atleast one pixel of tumor tissue. 
 - **Threshold** parameter is used to select regions of interest as bounding boxes cordinates. For example if threshold is set to 0.5, the bounding boxes of regions with more than 50% probability of having tumor tissues is returned. 

## Work in progress
- Converting all this into browser based model using Tensorflow js
- Trying out object detection based modeling instead of Classification (I think it is bit complicated because of the dimensionality of WSI in training the model. On resizing or cropping WSI images we might loose important details like nuclei count)

## Future Work
- Train Mnasnet on ICIAR2018 dataset where we have four classes: normal, benign, in situ carcinoma and invasive carcinoma. By doing this we can also add one more parameter which can let the user to select the class and set the threshold for that class. Eg., Return the regions where there is 50% likelihood of having invasive carsinoma.
## References

1. Multiclass Classification of Breast Cancer in Whole slide Images (https://github.com/scottykwok/bach2018/blob/master/Multiclass%20Classification%20of%20Breast%20Cancer%20in%20Whole%20slide%20Images.pdf)
2. Two-Stage Convolutional Neural Network for Breast Cancer Histology Image Classification. ICIAR 2018 Grand Challenge on BreAst Cancer Histology images (BACH) (https://github.com/ImagingLab/ICIAR2018)

