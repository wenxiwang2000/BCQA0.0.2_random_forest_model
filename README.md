# BCQA — Brightfield Cell Quality Assay

BCQA is a lightweight **AI-assisted cell morphology analysis tool** for bright-field microscopy.  
It performs **cell segmentation, morphology quantification, thickness heatmap visualization, and automated non-cell filtering using a trained Random Forest classifier.**

The tool is designed for **rapid cell quality assessment** without fluorescence labeling.
<img width="1190" height="591" alt="image" src="https://github.com/user-attachments/assets/607f6c1c-4065-451c-be51-1ba3e9d8018f" />

---

## 🚀 Key Features

- **Automatic Cell Segmentation**
  - Otsu or Adaptive thresholding
  - Morphological cleanup
  - Marker-controlled contour detection

- **Quantitative Cell Morphology Extraction**
  - Area
  - Perimeter
  - Circularity
  - Aspect ratio
  - Convex area
  - Equivalent diameter
  - Mean intensity (thickness proxy)

- **Thickness Heatmap Visualization**
  - Cells are filled with a greyscale map proportional to mean intensity  
  - Brighter cells → thicker → darker grey

- **Random Forest Quality Filtering (Novel Feature)**
  - Load a trained `.joblib` model
  - Automatically remove **non-cell objects or segmentation artifacts**
  - Keeps only high-confidence cell detections

- **Interactive Streamlit Interface**

---

## 🧠 Core Idea

After segmentation, each detected object is represented by a **morphology feature vector**.

These features are used by a **RandomForestClassifier** to distinguish:
<img width="2482" height="1287" alt="image" src="https://github.com/user-attachments/assets/34ee0844-4a8f-4a9e-aff9-45a5653404d6" />
<img width="1097" height="865" alt="image" src="https://github.com/user-attachments/assets/5a56dcb2-9841-42a2-8526-fbdde5ec9f73" />
<img width="1134" height="908" alt="image" src="https://github.com/user-attachments/assets/ecb1fbe2-680c-467a-9614-3a1f3f5c206a" />
<img width="1362" height="865" alt="image" src="https://github.com/user-attachments/assets/1abaa89f-15be-4a69-90ef-c8878799d779" />
