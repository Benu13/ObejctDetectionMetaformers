# ObejctDetectionMetaformers
Small project on MetaFormers usage for object detection. Learning object detection and segmentation by trying to connect MetaFormer backbone to YOLOv8 head. 
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
## Backbone
For the backbone of metaformer-based models CAFormer[4] is used. CAFormer architecture is based on two ConvFormer blocks and two TransFormer blocks. //tbc
## Convformer block 
MetaFormer backbone based models use MetaPolyp[5] Convformer block after each encoder block. This block is added to help extract local features from the information provided by MetaFormer backbone encoders. It is achieved by adding pointwise convolution, to which Self-Attention mechanism[6] is applied. Finally Channel MLP layer is used to help the model learn the fusion of the local information from backbone and the crucial information extracted from those two layers. 
<p align="left">
  <img src="https://github.com/Benu13/ObejctDetectionMetaformers/assets/39136856/e2b3c6dd-0dbe-4245-bd8e-f5768c90ed37">
  <em>Convformer architecture [5].</em>
</p>

## C2F
## Head

## Model 1
Model 1 architecture:
![CF_V1](https://github.com/Benu13/ObejctDetectionMetaformers/assets/39136856/ce385cd3-32d3-4a43-a127-f68b51e5ec9b)
  
Model 1 training metrics (20 epochs): 
![image](https://github.com/Benu13/ObejctDetectionMetaformers/assets/39136856/721d743a-5fb7-454b-a1f5-ba28b9feaff8)
  
Model 1 validation metrics (20 epochs):
![image](https://github.com/Benu13/ObejctDetectionMetaformers/assets/39136856/797132c7-cac8-49a8-a430-ed8af2506e5e)
  

## Model 2
Model 2 architecture:
// todo  
  
Model 2 training metrics (20 epochs): 
![image](https://github.com/Benu13/ObejctDetectionMetaformers/assets/39136856/9e44aaf4-f45a-4433-bcc6-9610233829ba)
  
Model 2 validation metrics (20 epochs):
![image](https://github.com/Benu13/ObejctDetectionMetaformers/assets/39136856/a44d421b-1349-4670-955e-49851a59cc3d)

## MetaPolyp architecture:
MetaPolyp architecture can be found in [5].  
MetaPolyp training metrics (20 epochs):

  
MetaPolyp validation metrics (20 epochs): 

  
#
[1]. Kaggle Competition - https://www.kaggle.com/competitions/hubmap-hacking-the-human-vasculature/  
[2]. Kaggle user: Mersico - https://www.kaggle.com/code/mersico/medical-instance-segmentation-with-yolov8  
[3]. https://github.com/qubvel/segmentation_models.pytorch  
[4]. MetaFormer Baselines for Vision, https://github.com/sail-sg/metaformer  
[5]. Meta-Polyp: a baseline for efficient Polyp segmentation: https://github.com/huyquoctrinh/MetaPolyp-CBMS2023  
