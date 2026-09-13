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

