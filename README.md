# ObejctDetectionMetaformers
Small project on MetaFormers usage for object detection. Learning object detection and segmentation. 
# Dataset
Data used in this project comes from Kaggle competition "HuBMAP - Hacking the Human Vasculature"[1].
For further tests two types of datasets where created. First one was COCO style dataset, used for object detection with YoloV8 and Final "YoloFormer". 
The structure of said dataset present as: 
<p align="left">
  <img src="https://github.com/Benu13/ObejctDetectionMetaformers/assets/39136856/ce181698-0cf8-4bae-b61d-3ff14f263790" />
</p>

Second dataset contained labeled and unlabeled data, annotations were converted to masks. Used for semantic segmentation. Unlabeled data were included in 
case of future test on semi-supervised lerning.

<p align="left">
  <img src="https://github.com/Benu13/ObejctDetectionMetaformers/assets/39136856/d0bfaac9-eb05-4517-b9bd-40194134125a" />
</p>

# YoloV8 
YoloV8 was implemented using Ultralytics package. For this version coordinates need to be normalized. Model was implemented with the help of tutorial[2].

# Unet
Tests on Unet++ with segmentation_model_pytorch package [3].  

# Metaformers on segmentation
Tests on using MetaFormers for segmentation. 

#
[1]. Kaggle Competition - https://www.kaggle.com/competitions/hubmap-hacking-the-human-vasculature/  
[2]. Kaggle user: Mersico - https://www.kaggle.com/code/mersico/medical-instance-segmentation-with-yolov8  
[3]. https://github.com/qubvel/segmentation_models.pytorch
