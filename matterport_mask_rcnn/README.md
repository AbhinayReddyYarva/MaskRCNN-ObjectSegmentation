# Mask R-CNN for Object Detection and Segmentation

Please clone or download the githiub matterport mask rcnn repo here (https://github.com/matterport/Mask_RCNN) and update below changes in respective files.

## /mrcnn/parallel_model.py
If you try to use multiple gpu to train the model then you will receive below error. 
##### RuntimeError: It looks like you are subclassing `Model` and you forgot to call `super(YourClass, self).__init__()`. Always start with this line.
To fix above error update /mrcnn/parallel_model.py file with below change in first line of def __init__(self, keras_model, gpu_count) in class ParallelModel(KM.Model)
##### super(ParallelModel, self).__init__()   

## /mrcnn/model.py
If you try to create mrcnn model object then you will receive below error.
##### AttributeError: 'ParallelModel' object has no attribute 'metrics_tensors'
To fix above error update /mrcnn/model.py file with change i.e., to initialize self.keras_model.metrics_tensors = [] in method compile(self, learning_rate, momentum) in class MaskRCNN()
##### self.keras_model.metrics_tensors = []
