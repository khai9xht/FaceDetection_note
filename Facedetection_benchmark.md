# **Face Detection Benchmark**
## **1. Metrics**
### **1.1 Precision-Recall (PR) Curve**
||||
|---|---|---|
|$_{GroudTruth}/Model$|1|0|
|1|TP|FP|
|0|FN|TN|

TP (True Positive) is an outcome where the model correctly predicts the positive class </br>
TN (True Negative) is an outcome where the model correctly predicts the negative class </br>
FP (False Positive)  is an outcome where the model incorrectly predicts the positive class </br>
FN (False negative) is an outcome where the model incorrectly predicts the negative class </br>

$Precision = \frac{TP}{TP + FP}$; $Recall = \frac{TP}{TP+FN}$

$F1 = 2*\frac{precision*recall}{precision+recall}$
</br></br></br>
### **1.2 mAP (mean Average Precision)**

$mAP = \frac{1}{n}\sum_{c \in classes}{Precision(c)}$ ~ $\frac{1}{n}\sum_{c \in classes}{\int_0^1Precision(c, k)dk}$

k: threshold</br>
n: number of classes
</br></br></br>

### **1.3 IoU (Intersection over Union)**

IoU = $\frac{AoO}{AoU}$

AoO: Area of overlap </br>
AoU: Area of Union

![](IoU.png)
</br></br></br>

### **1.4 Receiver Operating Characteristic (ROC) curve**
- is a graph showing the performance of a classification model at all classification thresholds. This curve plots two parameters:</br>

$TPR = \frac{TP}{TP + FN}$, $FPR = \frac{FP}{FP + TN}$

TPR: True Positive Rate </br>
FPR: False Positive Rate

- An ROC curve plots TPR vs. FPR at different classification thresholds. Lowering the classification threshold classifies more items as positive, thus increasing both False Positives and True Positives. The following figure shows a typical ROC curve.
- The Area Under the Curve (AUC) is the measure of the ability of a classifier to distinguish between classes and is used as a summary of the ROC curve.
- example:

![](ROCcurrveExample.png)
</br></br></br>

### **1.5 Inference Latency, light weight**
## **2. Datasets**
### **2.1. WIDER FACE**
- 32203 images, 393703 labels
- Train / Validate / Test ratio: 0.4 : 0.1 : 0.5  
- Image resolution: various
- annotation format: 
  - Path to image
  - list of bounding boxes
    - x1, y1, w, h, blur, expression, illumination, invalid, occlusion, pose
### **2.2. FDDB (benchmark dataset)**
- 2845 images, 5171 faces
- image resolution: various
- annotation format: 
  - Path to image
  - list of bounding boxes
    - x1, y1, w, h, blur, expression, illumination, invalid, occlusion, pose