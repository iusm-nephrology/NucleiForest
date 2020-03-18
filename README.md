# NucleiForest
Scikit-learn based Random Forest Classification for DAPI-stained nuclei ground-truth.
This algorithm is implemented using Python scripts in Jupyter Notebook's.

- The classification was performed using training and testing data from two different kidney biopsies.

- Each biopsy was classified into 3 different types of ground-truth namely;
  1) 2D Maximum Intensity Projection.
    - Everything other than nuclei of interest was masked in this case
    - Individual ground-truth image size: 32 x 32
  2) 3D Volume.
    - Everything other than nuclei of interest was masked in this case
    - Individual ground-truth image size: 32 x 32 x 7
  3) 3D Volume With Context.
    - No masked data in this case. Therefore, neighbouring nuclei were also present.
    - Individual ground-truth image size: 32 x 32 x 7
    
- Each ground-truth was classified into 8 different classes namely:
  1) S2S3
  2) TAL
  3) DCT
  4) CD
  5) CD45
  6) Nestin
  7) CD31_glom
  8) CD31_inter
  
- Random Forest Classifier was used from Scikit-learn (version 0.22.2) library. The version information is as follows:
  3.2.4.3.1. sklearn.ensemble.RandomForestClassifier
  
- Random Forest Classifier parameters used:
  1) The number of trees in the forest (n_estimators) = 200
  2) The maximum depth of the tree (max_depth) = None (default)
    - In case of default settings, the nodes are expanded until all leaves are pure or until all leaves contain less than
      min_samples_split samples. The number of min_samples_split samples were left as 2 by default.
      
- Approximately, 97000 training images and 32000 test images were used for each ground-truth type.

- The F1-score was on an average of 42.01% for all three types of ground-truth results combined.
  (Individual scores can be found in respective Jupyter Notebooks)
  
- The Balanced Accuracy was on an average of 33.63% for all three types of ground-truth results combined.
  (Individual scores can be found in respective Jupyter Notebooks)
  
- Please find confusion matrices explaining performance of Random Forest Classifier on each class in respective Jupyter Notebooks.

- The Python scripts for each of these 3 different types of ground truth are as follows:
  1) 2D Maximum Intensity Projection: RFCSklearn_F33F44_Mask2DMax.ipynb
  2) 3D Volume: RFCSklearn_F33F44_Mask3D.ipynb
  3) 3D Volume With Context: RFCSklearn_F33F44_All3D.ipynb
  
  (All three scripts having the exactly same implementation except modifications in the variable 'groundtruth_type'
  and filename used to save high-resolution images of confusion matrices. These three scripts are maintained solely
  for easy of use and keeping track of results.)
  
Thank You..!!
