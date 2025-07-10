
# Car Damage Classification with Custom CNN and ResNet50  
*(Please read the following paragraphs containing vital info about the project)*

---

## 📦 Required Files to Run the Notebook

1. 🔗 **[Final Dataset Used For CNN Model (Google Drive)](https://drive.google.com/file/d/1898L8prHBT9T8uW8jEIEEqsCF0PQhd6T/view?usp=drive_link)**  
   → Used directly to train and evaluate both models.

2. 🔗 **[Initial Dataset for Cleaning Demonstration (Google Drive)](https://drive.google.com/file/d/1WoaTT2RAeIpiiaOwghFmpRi6lbtu-P-Y/view?usp=drive_link)**  
   → Used in the first part of the notebook to show how the dataset was built (for transparency only).

3. 🔗 **[Train Set Shown with Augmentation (Google Drive)](https://drive.google.com/file/d/1MJy9WBvSyDxwd0j72zPs9Mhqi3lBcjrv/view?usp=drive_link)**  
   → Used to demonstrate offline data augmentation logic.

> ⚠️ **Important:**  
> The ipynb file was created originally in **Google Colab** free version, so to reproduce this in **Google Colab**, upload all 3 `.zip` files **directly to "My Drive"**, **not inside folders**, and do not rename them. This ensures the code paths work correctly.

If you're only interested in running the models, **you can skip the data preprocessing "First part" in the notebook and you now longer need raw datasets provided in the 2nd and 3rd links, just use the 1st link the "Final Dataset Used For CNN model".**

---

## 📌 Project Overview

This deep learning capstone project classifies car images into **6 damage categories**, using:

- A **custom CNN model** built from scratch
- A **fine-tuned ResNet50** model (transfer learning)

### 📁 Dataset Construction
Combined and curated from multiple Kaggle datasets:

- [Ripik Hackfest Dataset](https://www.kaggle.com/datasets/sudhanshu2198/ripik-hackfest)  
  → Used `Dent`, `Scratches`, `Tire_Flat`, `Glass_Shatter`, `Lamp_Broken`.  
  → `Dent` + `Scratches` were merged into **Surface_Damage**.

- [Car Damage Severity Dataset](https://www.kaggle.com/datasets/prajwalbhamere/car-damage-severity-dataset)  
  → Used `Severe Damage` → renamed to **Significant_Damage**

- [Comprehensive Car Damage Dataset](https://www.kaggle.com/datasets/samwash94/comprehensive-car-damage-detection)  
  → Used `F_Normal` and `R_Normal` → unified into **No_Damage**

---

## 💡 Inspiration

I aimed to apply image classification to a real-world problem in **economics and insurance**.  
Car insurance agencies face **losses due to human error or intentional fraud**. My model can be used as a **verification tool** — if the employee's report disagrees with the model prediction, the case can be **flagged for secondary review**. This reduces risk and cost from misreporting and helps streamline damage verification.

---

## 🧠 Key Features

- ✅ Deduplication using **ImageHash**
- ✅ Balanced train set with **manual validation/test splits**
- ✅ **Augmentation only** on the train set to simulate real-world variability
- ✅ Evaluation:
  - Per-class accuracy
  - Confusion matrix
  - Bootstrap 95% CI for overall accuracy
  - Binomial CI for per-class accuracy
- ✅ **External image tested** on both models to assess generalization

---

## 📊 Final Results

| Model        | Validation Accuracy | Test Accuracy |
|--------------|---------------------|----------------|
| Custom CNN   | 86.5%                | 84.7%          |
| ResNet50     | 93.9%                | 94.1%          |

---

## 🔧 Potential Improvements

- Add additional damage types (e.g. interior damage, missing parts)
- Increase training data size per class for better generalization
- Expand validation and test sets for **higher statistical reliability**
- Use the model as an **automated classifier**, not just a verification tool

---

## 🛠️ Requirements

Install required packages from `requirements.txt`:
```bash
pip install -r requirements.txt
