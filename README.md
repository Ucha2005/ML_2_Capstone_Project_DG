
# Car Damage Classification with Custom CNN and ResNet50

🔗 **[Download Final Dataset Used For CNN Model (Google Drive)](https://drive.google.com/file/d/1898L8prHBT9T8uW8jEIEEqsCF0PQhd6T/view?usp=drive_link)**
**[Download initial Dataset I constructed (Google Drive)](https://drive.google.com/file/d/1WoaTT2RAeIpiiaOwghFmpRi6lbtu-P-Y/view?usp=drive_link)**
**[Download Train Set Which is Going to be shown how it was augmented (Google Drive)](https://drive.google.com/file/d/1MJy9WBvSyDxwd0j72zPs9Mhqi3lBcjrv/view?usp=drive_link)**
The ipynb file in the 1st part shows how generally Initial dataset was cleaned (its no necessary to run for Model, it has demonstration purposes for transparency). 2nd part is the actual Model(s) and Analysis. 

---

## 📌 Project Overview 
This deep learning capstone project classifies images from a **cleaned 6 class car damage classification dataset** using:
- A custom CNN model built from scratch
- A fine-tuned ResNet50 transfer learning model
Data construction details:
https://www.kaggle.com/datasets/sudhanshu2198/ripik-hackfest 
From dataset link above I picked 4 major classes: Dent,scratches , Tire_Flat,Glass_Shatter, Lamp broken. Note I unified dents and scratches into "Surface_Damage(Dents, Scratches)" class.
https://www.kaggle.com/datasets/prajwalbhamere/car-damage-severity-dataset
From dataset link above I picked Severe damage class and used as "significant_damage" in my dataset.
https://www.kaggle.com/datasets/samwash94/comprehensive-car-damage-detection
From the link above I picked "R_Normal: Rear view of undamaged cars" , "F_Normal: Front view of undamaged cars" and unified them as "No_Damage" class in my dataset. 

It includes thorough preprocessing, robust evaluation (including confidence intervals), and external image testing.

## 🧠 Key Features
- Cleaning via perceptual image hashing (`ImageHash`)
- Offline manual dataset splitting into Train/Validation/Test sets
- Augmentation applied only to training set for generalization
- Evaluation using confusion matrix, per-class accuracy, bootstrap and binomial confidence intervals
- External (out-of-sample) image tested on both models
- Comparison between scratch CNN and ResNet50

## 📊 Results
| Model        | Validation Accuracy | Test Accuracy |
|--------------|---------------------|----------------|
| Custom CNN   | 86.5%                | 84.8%          |
| ResNet50     | 93.9%                | 94.1%          |

## 🛠️ Requirements
Install the required Python packages