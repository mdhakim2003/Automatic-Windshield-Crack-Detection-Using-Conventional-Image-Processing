# Automatic-Windshield-Crack-Detection-Using-Conventional-Image-Processing
Conventional image-processing system for detecting windshield cracks using bilateral filtering, Adaptive Canny edge detection, morphological processing, and contour analysis.

Use a README that is simple, academic, and easy for your lecturer or another student to understand. You can paste this directly into README.md and edit the filenames later.

# Automatic Windshield Crack Detection Using Conventional Image Processing

## Overview

This project develops an automatic windshield crack detection system using conventional image-processing techniques.

The system processes a vehicle windshield image and identifies possible crack regions using image preprocessing, Adaptive Canny edge detection, morphological processing, and contour analysis.

Unlike deep-learning approaches, this project does not require model training. The final decision is made using image-processing features and rule-based crack detection.

The system produces one of two outputs:

- **CRACK DETECTED**
- **NO CRACK DETECTED**

When a crack is detected, the detected crack region is highlighted on the windshield image.

---

## Project Objective

The main objectives of this project are:

1. To develop an image-processing system for detecting cracks on vehicle windshields using grayscale conversion, bilateral filtering, and Adaptive Canny edge detection.

2. To identify and highlight detected crack regions using morphological processing and contour analysis.

---

## System Workflow

The proposed image-processing pipeline is:

```text
Image Acquisition
        ↓
Resize Image
        ↓
Windshield ROI Extraction
        ↓
Grayscale Conversion
        ↓
Bilateral Filtering
        ↓
Adaptive Canny Edge Detection
        ↓
Morphological Closing
        ↓
Contour Detection
        ↓
Crack Region Filtering
        ↓
Candidate Crack Regions
        ↓
Crack Detection Criteria
       / \
     YES  NO
      ↓    ↓
  Crack   No Crack
 Detected Detected
      ↓
Display Inspection Result

Image Processing Techniques
1. Image Resizing

The input image is resized to 640 × 640 pixels to provide a consistent image size for processing.

2. Windshield ROI Extraction

Only the windshield region is selected for further processing. This reduces unnecessary edges from other parts of the vehicle.

3. Grayscale Conversion

The windshield image is converted into grayscale to reduce image complexity and focus on intensity and edge information.

4. Bilateral Filtering

A bilateral filter is applied to reduce image noise while preserving important crack edges.

5. Adaptive Canny Edge Detection

Adaptive Canny edge detection is used to identify possible crack edges. The lower and upper thresholds are automatically calculated based on the image intensity.

6. Morphological Processing

Morphological closing is applied to connect broken crack edges and reduce small gaps between detected regions.

7. Contour Detection

Contours are extracted from the processed edge image to identify possible crack regions.

8. Crack Region Filtering

The detected contours are filtered based on several properties, including:

Contour area
Contour length
Extent
Position within the windshield ROI
Edge density
Number of long contours

Small or unsuitable regions are removed before the final crack decision is made.

Detection Output

The system displays several processing stages for visual inspection:

Windshield ROI
Grayscale Image
Bilateral Filtered Image
Adaptive Canny Output
Morphological Closing
Candidate Crack Regions
Final Crack Detection Result

The Candidate Crack Regions stage displays small bounding boxes around possible crack regions.

The final stage combines the accepted regions and highlights the overall detected crack area.

Dataset

The windshield images used in this project are obtained from the Windshield Damages Dataset available on Roboflow Universe.

The dataset contains approximately 577 windshield damage images captured under different:

Lighting conditions
Viewing angles
Backgrounds
Reflection conditions
Crack shapes and patterns

Dataset:

PASTE YOUR ROBOFLOW DATASET LINK HERE

Technologies Used
Python
OpenCV
NumPy
Matplotlib
Scikit-learn
Jupyter Notebook
