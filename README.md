![WIP](https://img.shields.io/badge/status-work--in--progress-orange)
# A bunch of AI disease detectors for a variety of conditions
* Full Body Fracture 
* Brain Tumor
* Skin Disease
* Pneumonia
* Lung Nodules
* Leukemia

# Why was this built?

## The Problem
* Radiologists are constantly under stress
* Misdiagnoses leads to wasted time going to other visits (Not to mention the costs)
* Not every place has world-class radiologists on site
<p align="center">
 <img src = "https://outcomesrocket.health/wp-content/uploads/2020/04/Reducing-Misdiagnosis-in-Radiology-and-Beyond-1.png" width = "100%" height = "auto">
</p>

## The Solution 
### Implement AI
* Computers don't get tired. A YOLO model will look at the 1,000th image with the same focus as the 1st one. It spots the subtle patterns that a human eye might gloss over due to exhaustion or human error.

# Website Link
![WIP](https://img.shields.io/badge/status-work--in--progress-orange)

# Models

## Full-Body-Fracture-Detector
An Ensemble of AIs that can be used for a variety of fracture types
1. Avulsion fracture
2. Comminuted fracture
3. Compression (crush) fracture
4. Fracture dislocation
5. Greenstick fracture
6. Impacted fracture
7. Intra-articular fracture
8. Longitudinal fracture
9. Oblique fracture
10. Segmental fracture
11. Spiral fracture
12. Transverse fracture
13. No Fracture 
### Dataset
* https://huggingface.co/datasets/RyanChen1209/BIG-X-RAY-DATASET

# The Setup
<div align="center">
  <video 
    src="https://github.com/user-attachments/assets/6371d4fd-a2e0-4f86-b5f7-192a75df57a1"  
    width="100%" 
    muted 
    autoplay 
    loop 
    playsinline
    title=""
    style="pointer-events: none; border-radius: 12px;"
  >
  </video>
</div>


### 1. The Frontend
* This is the website where the user or technician interacts with the tool. It needs a clean upload area for the X-ray. Its job is to handle the file, send it to the backend for processing, and then display the final results like the image overlays and the summary.

### 2. The Bounding Box Model (YOLO Model)
* A YOLO model determines bounding boxes for the fractures in the image. There can be multiple bounding boxes if there's multiple fractures

### 3. The Classifier
* An AI model gets fed copies of the same image, but for every fracture found, the system generates a unique copy of the original image. For example, on "Image 1," the system draws only the first bounding box. On "Image 2," it draws only the second, and so on. These images get classified by the AI on what type of fracture is present.

### 4. The Reporter (LLM)
* After the detection is done, you have raw data (like coordinates and labels). This data is fed into a language model (Like llama). It takes those technical results (Along with a potential clinical note) and writes a clear, professional summary that explains the findings in plain English.

### 5. The Output (Result Display)
* The final step sends everything back to the website. The user sees the original X-ray with a red box highlighting the break, the type of fracture, and the written report sitting right next to it.

### Preview
https://github.com/user-attachments/assets/889ffcdc-222d-4ada-b341-ac72b339823b

## Brain Tumor Classification and Segmentatation
### Types of tumors it will classify
* Glioblastoma
* Glioma
* Meningioma
* Pituitary
* Schwannoma
* Metastatic
* No tumor

### Dataset
* https://huggingface.co/datasets/RyanChen1209/Brain-Tumor-Classification-MRI

### Structure
* A classifer detects whether a tumor is present in the first place as well as the type
* If a tumor is present, it gets sent to a segmentation model (UNet) to generate a mask
* LLM summarizes findings


# Contributors
### Thank you to
* Partho Biswas
* Ambrose Sukraj
* Alikhan Zhumabayev
* And Many Other Supporters!
