# Downlaod Dataset
<< https://zenodo.org/records/12735702

# Downlaod Our saved best model
<< https://drive.google.com/file/d/1-yq1hIik4DdBhR0sjxLZPFNdtKz4xkTQ/view?usp=drivesdk

# About My Project 
Developed a  Brain MRI Tumor Detection system 
Using EfficientNet B3 Pretrained Model.(Fine Tunning)

# Our  Goal 
Automatically detects the presence of a tumor in a brain MRI image.
it is trained over 4 classes..
Glioma Tumor  , Meningioma Tumor ,  Pituitary Tumor , No Tumor.
This model will detect  whch type of tumor the person  has .
if there is no tumor it will  tell that No Tumor has been detected.

# Model Accuracy : 

  Validation Accuracy : 89 .25 %
  Test Accuracy       : 88 .42 %
  Precision/Recall/confusion Matrix  : See Accuracy csv files in my Repo
    
# How to do Prediction.

1 . Clone My repo into your Local  Machine and 
by using local ide ( use jupiter notebook ) 
it will save u to install extra dependencies. 

2. Download my trained model "best_model.keras"
using upper google drive link and save model into your
local folder (project folder)
3 .Go into your local ide (uplaod "best_model.keras")
also uplaod the test image which u wants to predcit.
take test imsges into my given upper link .
   
# write Code :
     from tensorflow.keras.models import load_model
     import cv2
     import numpy as np
     model = load_model("best_model.keras")
     img = cv2.imread("your test path past here")   
     img = cv2.resize(img, (224, 224)) 
     img = img / 255.0        
     img = np.expand_dims(img, axis=0)
     pred = model.predict(img)
     print("Raw Prediction:", pred)
    if pred[0][0] > 0.5:
      print("Prediction: yes Tumor Detected")
    else:
      print("Prediction: No Tumor Detected")


