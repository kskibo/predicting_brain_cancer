# Predicting & Detecting Brain Cancer
**Kaytlynn Skibo**

---
 ## Using Neural Networks to Predict if an MRI scan of a Brain contains a tumor and detect where it is located. 
 
---
A note for anyone attempting to recreate the results of this notebook: please note that much of this code that was run in the notebook can be quite demanding.

---


+ **Data** : 
  + Source : [Kaggle]('https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset?select=Testing')
  + Size : 7023 images
  + Labels : `['glioma', 'meningioma', 'notumor', 'pituitary']`
  + Target : Accurately predicting the diagnosis of an MRI scan based on the images, then using Grad-CAM to visualize the weights.
  
**Libraries Used**
+ Pandas
+ Numpy
+ Matplotlib
+ Scikit Learn
+ tensorflow.keras
+ google.colab
+ seaborn
+ PIL
+ itertools
  
**Model Performance on Data**
+ Baseline: 0.28
+ `X` : images in the brain scan directory
+ `y` : the folder in which the image are located in
+ random_state = 2023
+ 4 classes
+ Parameters : 
  + Optimizer: `adam`
  + Filters: `5`
  + Kernel Size : `(3,3)`
  + Drop Outs: `.25`
  + BatchNormilization: No
  + Regularization: No
  + Rescaling : Yes
  + Epochs : 32
+ Training `acc/loss` : 0.9619 / 0.0932
+ Validation `acc/loss` : 0.9594 / 0.1910

---

**Primary Findings**
1. Neural Netorks can predict brain cancer in MRI scans with high accuracy.
1. Global Average Pooling is necessary for Grad-CAM to function.
3. The weights of the model seemed to be affected by extreme brightness and darkness in MRI scans.
4. Adjusting the data by rotating the images, flipping them, and increasing/decreasing contrast seemed to worsen the model's performance and learning.

**Recommendations**
- Use this Model to work alongside your doctors. It can help reassure them of their diagnosis or check them before they make an incorrect diagnosis. 


**Conlusions**
+ A neural network can be used to accurately predict if cancer is in an MRI scan, and give its assumption of where it might be located in the image. 

**Next Steps**
- More training: Because this will be usede and relied upon in a medical context, I feel getting the accuracy as high and close to 100% as I can. I'd also like to continue to reduce loss if possible. 
- App Development : an application where doctors and techs could interact directly with the model and can easily input an image to get results would be ideal. 

---

**In this Repository**
- `code` : 
  - `01_Problem_Statement` : In this notebook we will be discussing the projects objectives, goal, and intended audience.
  - `02_Modeling_Visualization` : In this notebook, the images from directory will be put through and image dataset generator and modeled using CNN. The various models will change and tune layers to achieve the highest accuracy score with the lowest loss in the validation set. These models will then be visualized using some graphing functions below to see how well the model performs. 
  - `03_Grad_Cam` : In this notebook we will be using Grad Cam (Gradient-weighted Class Activation Mapping) to make heatmap visuals of the last layer in the model. The goal of this notebook is to overlay the heatmaps on on the MRI scans to hopefully indicate where the tumors may be located at. 
  - `04_Conclusion` : In this notebook we will be discussing the findings of the data and the model, reviewing the problem statement, and measuring our success.

- `data` : this folder contains all models created throughout the project
  - `modelA`
  - `modelB`
  - `modelC`
  - `best_weights.h5`

- `images` : this folder contains all images downloaded from the dataset 
  - `brain_scans` : contains the 4 different classes and their images.
  - `visuals` : the visuals of the data made in `02_Modeling_Visualizations`
  - `presentation` : a google slides presentation to discuss and walk through the project


