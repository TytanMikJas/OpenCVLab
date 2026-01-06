# Computer Vision & Image Processing Projects

This repository contains a collection of computer vision projects and laboratory exercises implemented in Python using **OpenCV** and **scikit-image**. The notebooks cover fundamental to advanced image processing techniques ranging from basic binarization to feature extraction and image stitching.

## 📂 Repository Structure

### 1. Image Binarization
- **File:** `01_Binarisation.ipynb`
- **Description:** - Investigation of grayscale and color image binarization methods.
  - Focuses on separating objects from the background and isolating individual objects.
  - Includes experimental analysis of parameter selection for thresholding algorithms (beyond simple `cv2.threshold` usage).

### 2. Edge Detection & Histogram Analysis
- **File:** `02_Edge_Detection.ipynb`
- **Description:**
  - **Parts 1-3:** Implementation of edge detection algorithms.
  - **Part 4:** Global operations focusing on histogram transformations and further binarization techniques.

### 3. SLIC Superpixel Segmentation
- **File:** `03_SLIC_Segmentation.ipynb`
- **Description:**
  - Segmentation of images (e.g., 'tabby', 'caries') using the **SLIC (Simple Linear Iterative Clustering)** algorithm.
  - The goal is to obtain uniform superpixels that contain either only parts of the object or only the background.
  - Analysis of the algorithm's behavior with varying numbers of superpixels and sigma parameters.
  - Utilization of `skimage.segmentation.slic` and boundary visualization.

### 4. Classic Object Detection (Morphology & Blobs)
- **File:** `04_Classic_Detection.ipynb`
- **Description:**
  - A pipeline for generating synthetic training data for amodal segmentation.
  - **Tasks:** Detection and segmentation of specific objects (larvae) from source images.
  - **Pipeline:** Color binarization -> Connected Components (`cv2.findContours`) -> Blob Analysis.
  - **Filtering:** Removal of noise, merged instances, and non-target objects.
  - **Measurements:** Estimation of object properties such as length (via skeletonization), thickness, and shape classification (I-shape, S-shape, C-shape).

### 5. Hough Transform (Lines & Circles)
- **File:** `04_Hough_Detection.ipynb`
- **Description:**
  - Application for analyzing snooker positions.
  - **Goal:** Detect balls and table cushions (bands).
  - **Methods:** - Edge detection preprocessing.
    - **Hough Line Transform** (`cv2.HoughLines`) for detecting cushions.
    - **Hough Circle Transform** (`cv2.HoughCircles`) for detecting balls.
  - Includes parameter calibration and visualization of detected geometry on the input images.

### 6. SIFT Feature Detection (Research)
- **File:** `05_SIFT_POI_Detection.ipynb`
- **Description:**
  - Research and basic usage of the **SIFT (Scale-Invariant Feature Transform)** algorithm via `cv2.SIFT_create`.
  - Detection of KeyPoints (`detect`) and computation of Descriptors (`compute`).
  - Visualization of features using `cv2.drawKeypoints`.

### 7. Image Stitching (SIFT Implementation)
- **File:** `05_SIFT_HARD_EXAMPLE.ipynb`
- **Description:**
  - A practical project focused on **Image Stitching** (Panorama creation).
  - Uses a custom dataset of a static scene captured from different offsets and angles.
  - **Workflow:** 1. Detect SIFT keypoints and descriptors.
    2. Match features between the base image and offset images.
    3. Calculate geometric transformations (Homography).
    4. Merge images to create a unified view.
