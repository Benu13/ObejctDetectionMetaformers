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

[1]. Kaggle Competition - https://www.kaggle.com/competitions/hubmap-hacking-the-human-vasculature/
