# Full-Body-Fracture-Detector
An Ensemble of AIs that can be used for a variety of fracture types

# The Problem
* Radiologists are constantly under stress
* Misdiagnoses leads to wasted time going to other visits (Not to mention the costs)
* Not every place has world-class radiologists on site
<p align = "center">
 <img src = "https://outcomesrocket.health/wp-content/uploads/2020/04/Reducing-Misdiagnosis-in-Radiology-and-Beyond-1.png" width = "100%" height = "auto">
</p>

# The Solution 
### Implement AI
* Computers don't get tired. A YOLO model will look at the 1,000th image with the same focus as the 1st one. It spots the subtle patterns that a human eye might gloss over due to exhaustion.

# The Setup
### 1. The Frontend
* This is the website where the user or technician interacts with the tool. It needs a clean upload area for the X-ray. Its job is to handle the file, send it to the backend for processing, and then display the final results like the image overlays and the summary.

### 2. The Body Part Classifier
* Once the image is uploaded, it hits this first AI model. This is a general classifier that looks at the whole image and identifies exactly what part of the body it’s looking at (like a shoulder, hand, or knee). This is crucial because it decides which specialized tool needs to be used next.

### 3. The Bounding Box Model (YOLO Model)
* This is where the actual detection happens. Based on what the classifier found, the system picks a specific model trained only for that body part. This model scans the image to find which fracture it is, and a YOLO model is introduced to find the exact location of a fracture. It draws a "bounding box" around the break.

### 4. The Reporter (MedGemma)
* After the detection is done, you have raw data (like coordinates and labels). This data is fed into MedGemma, a language model trained on medical text. It takes those technical results (Along with a potential clinical note) and writes a clear, professional summary that explains the findings in plain English.

### 5. The Output (Result Display)
* The final step sends everything back to the website. The user sees the original X-ray with a red box highlighting the break, the type of fracture, and the written report sitting right next to it.
