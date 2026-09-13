# Automatic Windshield Crack Detection Using Conventional Image Processing

## Overview

This project develops an automatic windshield crack detection system using conventional image-processing techniques.

The system processes vehicle windshield images and identifies possible crack regions using image preprocessing, Adaptive Canny edge detection, morphological processing, and contour analysis.

Unlike deep-learning approaches, this project does not require model training. The final detection decision is made using image-processing features and rule-based crack detection.

The system produces one of two outputs:

- **CRACK DETECTED**
- **NO CRACK DETECTED**

When a crack is detected, the detected crack region is highlighted on the windshield image.

---

## Project Objectives

The main objectives of this project are:

1. To develop an image-processing system for detecting cracks on vehicle windshields using grayscale conversion, bilateral filtering, and Adaptive Canny edge detection.

2. To identify and highlight detected crack regions using morphological processing and contour analysis.

---

## System Workflow

The proposed image-processing pipeline is:

```text
START
  ↓
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
      \    /
       ↓
Display Inspection Result
       ↓
      END
```

---

## Image Processing Techniques

### 1. Image Resizing

The input image is resized to **640 × 640 pixels** to provide a consistent image size for processing.

### 2. Windshield ROI Extraction

The windshield Region of Interest (ROI) is extracted from the resized image. This helps reduce unnecessary edges from other vehicle parts and allows the system to focus mainly on the windshield area.

### 3. Grayscale Conversion

The windshield ROI is converted into grayscale to reduce image complexity and focus on intensity and edge information.

### 4. Bilateral Filtering

A bilateral filter is applied to reduce image noise while preserving important edge information. This is useful because windshield cracks normally appear as thin and irregular lines.

### 5. Adaptive Canny Edge Detection

Adaptive Canny edge detection is used to identify possible crack edges.

Instead of using fixed Canny threshold values, the lower and upper thresholds are automatically calculated based on the median intensity of the filtered image.

### 6. Morphological Processing

Morphological closing is applied after edge detection to connect small gaps between detected edges and improve the continuity of possible crack regions.

### 7. Contour Detection

Contours are extracted from the morphological output to identify connected regions that may represent windshield cracks.

### 8. Crack Region Filtering

Not every contour represents a crack. Detected contours are filtered using several properties, including:

- Contour area
- Contour length
- Contour extent
- Position inside the windshield ROI
- Edge density
- Number of long contours

Small or unsuitable regions are removed before the final crack detection decision is made.

### 9. Candidate Crack Regions

Regions that satisfy the contour filtering conditions are displayed using small bounding boxes.

This stage shows the individual regions that the system considers possible crack features before producing the final detection result.

### 10. Final Crack Detection

The final decision is based on several detection criteria:

- Minimum edge density
- Minimum number of valid crack regions
- Minimum number of long contours

If all required conditions are satisfied, the system displays:

**CRACK DETECTED**

If the conditions are not satisfied, the system displays:

**NO CRACK DETECTED**

When a crack is detected, the accepted candidate regions are combined and a larger bounding box is displayed around the overall detected crack area.

---

## Detection Pipeline Output

For a single windshield image, the system displays the following processing stages:

1. Windshield ROI
2. Grayscale Image
3. Bilateral Filtered Image
4. Adaptive Canny Edge Detection
5. Morphological Closing
6. Candidate Crack Regions
7. Final Crack Detection Result

The **Candidate Crack Regions** stage displays small bounding boxes around possible crack regions.

The final output combines the accepted regions and highlights the overall detected area.

---

## Dataset

The windshield images used in this project are obtained from the **Windshield Damages Dataset** available on Roboflow Universe.

The dataset contains approximately **577 windshield damage images** with different:

- Crack patterns
- Viewing angles
- Lighting conditions
- Backgrounds
- Reflection levels
- Windshield conditions

Dataset link:

https://universe.roboflow.com/myownworkspace-c190b/windshield-damages

The dataset is used to develop, tune, and evaluate the conventional image-processing algorithm.

---

## Technologies Used

The project is developed using:

- Python
- OpenCV
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook

---


## Requirements

```text
opencv-python
numpy
matplotlib
scikit-learn
jupyter
```

---


## Limitations

The detection system may be affected by several conditions, including:

- Strong windshield reflections
- Shadows
- Windshield wipers
- Dashboard edges
- Vehicle body edges
- Background objects
- Poor lighting
- Low image quality
- Crack-like lines or reflections

Since Adaptive Canny detects strong edges, some non-crack objects may also produce edges that are similar to windshield cracks.

---

## Future Improvements

Possible improvements for this project include:

- Improving automatic windshield ROI extraction
- Reducing reflections and shadows
- Further optimizing contour filtering parameters
- Testing with a larger number of normal windshield images
- Improving crack localization
- Improving false-positive rejection
- Testing the system under more environmental conditions
- Exploring additional conventional feature extraction techniques

---

## Academic Project

This project was developed as part of the **Machine Vision Technology** course at **Universiti Kuala Lumpur Malaysia France Institute (UniKL MFI)**.

The project focuses on **conventional image-processing techniques** and does not use deep learning for crack detection.

---

## Author

**Muhammad Danish Hakim**

Universiti Kuala Lumpur Malaysia France Institute  
**UniKL MFI**
