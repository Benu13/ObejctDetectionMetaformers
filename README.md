# ObejctDetectionMetaformers
Small project on MetaFormers usage for object detection. Learning object detection and segmentation by trying to connect MetaFormer backbone to YOLOv8 head. 
# Dataset
Data used in this project comes from Kaggle competition "HuBMAP - Hacking the Human Vasculature"[1].
For further tests two types of datasets where created. First one was COCO style dataset, used for object detection with YoloV8 and Final "YoloFormer". 
The structure of said dataset present as: 
![image](https://github.com/Benu13/ObejctDetectionMetaformers/assets/39136856/a0b9d589-ac57-4b1a-ade9-c777ccce2a25)
  
  
Second dataset contained labeled and unlabeled data, annotations were converted to masks. Used for semantic segmentation. Unlabeled data were included in 
case of future test on semi-supervised lerning.

Code used for creation of both dataset is included in file "DatasetCreation.ipynb".

# YoloV8 
YoloV8 was implemented using Ultralytics package. For this version coordinates need to be normalized. Model was implemented with the help of tutorial[2].

# Unet
Tests on Unet++ with segmentation_model_pytorch package [3].  

# Metaformers on object detection
Tests on using MetaFormers for object detection. 
## Backbone
For the backbone of metaformer-based models CAFormer[4] is used.
  
## Convformer block 
MetaFormer backbone based models use MetaPolyp[5] Convformer block after each encoder block. This block is added to help extract local features from the information provided by MetaFormer backbone encoders. It is achieved by adding pointwise convolution, to which Self-Attention mechanism[6] is applied. Finally Channel MLP layer is used to help the model learn the fusion of the local information from backbone and the crucial information extracted from those two layers. 
  
## Head
Head is taken from a YoloV8 model architecture. 
## Model
Model architecture:
![image](https://github.com/Benu13/ObejctDetectionMetaformers/assets/39136856/8ecd3a30-fe78-4653-b46c-c7d5e1191704)

The model implementation and function for training is included in file "YoloFormer.ipynb"
  
#
[1]. Kaggle Competition - https://www.kaggle.com/competitions/hubmap-hacking-the-human-vasculature/  
[2]. Kaggle user: Mersico - https://www.kaggle.com/code/mersico/medical-instance-segmentation-with-yolov8  
[3]. https://github.com/qubvel/segmentation_models.pytorch  
[4]. MetaFormer Baselines for Vision, https://github.com/sail-sg/metaformer  
[5]. Meta-Polyp: a baseline for efficient Polyp segmentation: https://github.com/huyquoctrinh/MetaPolyp-CBMS2023  
