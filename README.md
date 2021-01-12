# Masked_Faces
The goal of this project was to train YOLOv4 on a custom dataset containing images of two classes ( Masked and Un-masked ).I trained yolov4 using this (https://github.com/AlexeyAB/darknet) repository. You can find more details about the darknet on https://pjreddie.com/darknet/yolo/. (https://github.com/theAIGuysCode/YOLOv4-Cloud-Tutorial) helped me for Training Yolo on google colab.
# Dataset
I used MAFA dataset which can be downloaded from kaggle (https://www.kaggle.com/rahulmangalampalli/mafa-data).This data contains annotations in a .mat file. Yolo accept a specific dataset format for images and annotations. You can find all the details about Yolov4 data formats and other thing from this medium blog (https://towardsdatascience.com/yolov4-in-google-colab-train-your-custom-dataset-traffic-signs-with-ease-3243ca91c81d). I transformed the annotations of MAFA data into yolov4 fomrat using my own script. The transformed dataset can be downloaded from this (https://drive.google.com/file/d/1bVTUwwH9CI0jIQC3XJtycu2btZtVpTiR/view?usp=sharing) drive link.
# Training
Training yoloV4 on a custom dataset involves dealing with different thinng like updating the architecture of your detection model depending upn the size and number of classes of your dataset. You can find all the recommended chages on the official darknet repository by AlexeyAB (https://github.com/AlexeyAB/darknet#how-to-train-to-detect-your-custom-objects).After making all the recommended changes by the author, I trained the model for 60000 iterations. The final weights gave me an mAP of 72.79%.

     detections_count = 45332, unique_truth_count = 8493  
    class_id = 0, name = Masked, ap = 98.20%   	 (TP = 6245, FP = 281) 
    class_id = 1, name = Un-Maked, ap = 47.38%   	 (TP = 883, FP = 345) 

     for conf_thresh = 0.25, precision = 0.92, recall = 0.84, F1-score = 0.88 
     for conf_thresh = 0.25, TP = 7128, FP = 626, FN = 1365, average IoU = 75.15 % 

     IoU threshold = 50 %, used Area-Under-Curve for each unique Recall 
     mean average precision (mAP@0.50) = 0.727884, or 72.79 % 
    Total Detection Time: 113 Seconds

    Set -points flag:
     `-points 101` for MS COCO 
     `-points 11` for PascalVOC 2007 (uncomment `difficult` in voc.data) 
     `-points 0` (AUC) for ImageNet, PascalVOC 2010-2012, your custom dataset
# Improvements
As you can see the mAP for masked class is less from un-masked. This is because of the non-uniform distribution of data. This can be improved by incresing the number of images containing un-masked faces.
# Testing
You can test the model using this (https://drive.google.com/file/d/1-GsG5gZiyDzCrNnWt6RnllFnIbjjLN0y/view?usp=sharing) weight file. You can use darkent test or demo command for running detections on both images or videos respectively.
# Images
![alt_text](https://github.com/EhsanAlahi/Masked_Faces/blob/main/Image.png)
![alt_text](https://github.com/EhsanAlahi/Masked_Faces/blob/main/Image2.png)
# Videos
[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/dvYqJnsVKSQ/0.jpg)](https://www.youtube.com/watch?v=dvYqJnsVKSQ)
[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/5PlK9ugGBRk/0.jpg)](https://www.youtube.com/watch?v=5PlK9ugGBRk)
