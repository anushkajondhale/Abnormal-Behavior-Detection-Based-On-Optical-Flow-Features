# Abnormal-Behavior-Detection-Based-On-Optical-Flow-Features

This project (finished Dec 19, 2017) implements an abnormal-behavior detection system for crowds using optical-flow features and machine learning classifiers.

Summary
- Uses optical flow and morphological processing to extract motion features from video frames.
- Segments inhomogeneous crowds and represents each detected person with UV optical-flow features.
- Trains classifiers (SVM, Logistic Regression, KNN) with grid-search hyper-parameter tuning and evaluates ROC/AUC and accuracy.

Requirements
- Python 3.6 (3.6.1 recommended)
- See `requirements.txt` for the main Python packages.

Quick setup (conda recommended)

1. Create environment:

   conda create -n abd_env python=3.6
   conda activate abd_env

2. Install dependencies with pip (from project root):

   pip install -r requirements.txt

Usage

From the project root, run the main demo which processes the 200-frame sample video and shows detection results:

   python code/core.py

Notes
- The project expects reference data in the `ref_data/` folder (optical flow MAT files, foreground images, original frames). Do not move those paths unless you update `code/core.py` `load_data()` accordingly.
- To only extract features or run specific modules, see `code/Feature_extraction.py`, `code/getFeatureUV.py`, and `code/Classifiers.py` for callable functions.

Project structure (important files)
- `code/core.py`: main demo and entry point
- `code/Feature_extraction.py`: feature extraction logic and position detection
- `code/Classifiers.py`: classifier wrappers and evaluation
- `ref_data/`: optical flow data and sample frames used by the demo

License / Contact
- No license provided. For questions or improvements, open an issue or contact the original authors.
# Abnormal-Behavior-Detection-Based-On-Optical-Flow-Features
This project applied computer vision and mechine learning methods aimed to detect abnormal behaved object in crowd. (Finished on Dec.19 2017)

The goal of our work is to establish a video system that can distinguish abnormal behaving people from normal ones. We focused on a privacy-preserving video system and obtained the internal information of video with image processing techniques. Using optical flow features, we estimated and segmented inhomogeneous crowds composed of pedestrians that travel in different directions. With these features, we applied several classifying algorithms to tell the normal behaviour from the abnormal. In this process, we used grid search method to find the best hyper-parameter. We validated both the crowd segmentation algorithm, and the crowd counting system, on a large pedestrian dataset (200 frames of video, containing 4,988 total pedestrian instances). This project could help monitoring abnormal behaved objects in public environment with vision information.

- Language: Python3.6.1 

- Dependencies: OpenCV, Scikit-Learn, Scikit-Image, and Numpy (Anaconda recommanded) 

- Feature extraction: Morphological filter, Normalisation, Optical Flow 

- Classification Model: SVM, LogisticRegression, KNN 
