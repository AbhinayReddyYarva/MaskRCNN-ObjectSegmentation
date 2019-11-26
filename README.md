# MaskRCNN-ObjectSegmentation
Creating own fake dataset with segment annotations json files on required objects to detect with appropriate backgrounds to increase the accuracy of the model. I have tried using matterport mask rcnn and got pretty good results. 

Below are few predicted results:

![](synthetic_dataset/test/segmented_test_output_images/07.png)![](synthetic_dataset/test/segmented_test_output_images/02.png)![](synthetic_dataset/test/segmented_test_output_images/01.png) 

#### Dataset creation
For this sample model I have selected 4 different objects i.e., mug, red bottle, viop, mouse(wireless mouse). I have cropped the object images to extract just the object and got different background images. 

![](synthetic_dataset/input/foregrounds/utilities/mug/03.png) ![](synthetic_dataset/input/foregrounds/utilities/red_bottle/01.png) ![](synthetic_dataset/input/foregrounds/electronics/voip/03.png) ![](synthetic_dataset/input/foregrounds/electronics/mouse/02.png) ![](synthetic_dataset/input/backgrounds/IMG_20191120_101657.jpg)

These cropped objects will be placed on background images randomnly with different object combinations and mask images will also get created with mask definitions .json file in coco dataset annotations format i.e., (synthetic_dataset/train/mask_definitions.json) for training set and (synthetic_dataset/val/mask_definitions.json) for validation set.

![](synthetic_dataset/train/images/00000002.jpg)![](synthetic_dataset/train/masks/00000002.png) ![](synthetic_dataset/val/images/00000298.jpg, synthetic_dataset/val/masks/00000298.png)

