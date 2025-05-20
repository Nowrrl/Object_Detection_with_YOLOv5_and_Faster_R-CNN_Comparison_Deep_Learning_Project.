# Object Detection with YOLOv5 and Faster R-CNN: A Comparative Study

## Project Overview
This project aims to design and compare object detection models trained from scratch and using transfer learning.  
We applied **YOLOv5** and **Faster R-CNN** on two everyday objects: **Axe deodorant** and **Mouse**.  
The goal was to evaluate the effects of augmentation and training strategies on detection accuracy.  

---

## Dataset  
**Objects:** Axe deodorant and Mouse  
**Images:** 50 images (25+ per object) taken from various angles and distances  
**Resolution:** 416x416 pixels (to match YOLOv5 input requirements)  
**Labeling Tool:** LabelImg  
**Format:** Pascal VOC (.xml)  

---

## Data Augmentation Techniques  
To improve model generalization, the following augmentations were applied:  
- **Flips:** Horizontal and Vertical  
- **Rotations:** +45° and -45°  
- **Brightness Adjustments:** Increasing and Decreasing  
- **Image Enhancements:** Sharpening and Blurring  
- **Color Adjustments:** Hue and Saturation shifts  

---

## Model Training  
**Trained Models:**  
1. **YOLOv5 (Scratch)** - 10 epochs  
2. **YOLOv5 (Fine-Tuned)** - 10 epochs  
3. **Faster R-CNN (Scratch)** - 15 epochs  
4. **Faster R-CNN (Fine-Tuned)** - 15 epochs  

**Hyperparameters:**  
- **Batch size:** 16  
- **Learning rate:** 0.005  
- **Optimizer:** SGD  

---

## Evaluation Metrics  
The following metrics were used to evaluate model performance:  

- **Precision**  
- **Recall**  
- **F1 Score**  

| Model                     | Precision | Recall | F1 Score |
|--------------------------|----------|-------|---------|
| YOLOv5 Fine-Tuned        | ~0.70    | ~0.80 | ~0.70   |
| YOLOv5 Scratch           | ~0.00    | ~0.00 | ~0.00   |
| Faster R-CNN Scratch     | 0.538    | 0.667 | 0.594   |
| Faster R-CNN Fine-Tuned  | 0.636    | 0.667 | 0.651   |

---

## Results and Observations  
Fine-tuned models consistently outperformed scratch models.  
- **YOLOv5 Fine-Tuned:** Accurate detections, faster inference.  
- **Faster R-CNN Fine-Tuned:** Strong detection with slower inference.  
- **Scratch Models:** Performed poorly, highlighting the importance of transfer learning.  

### Visual Inference  
- **YOLOv5 Fine-Tuned** detected objects correctly.  
- **Faster R-CNN Fine-Tuned** showed accurate predictions with proper labeling.  
- **Scratch models** had inconsistent results, with YOLOv5 Scratch failing entirely.  

---

## Challenges  
Lighting inconsistencies posed a challenge, but were mitigated using brightness and shadow augmentation.  
Object occlusion was addressed by including multiple perspectives and rotations.  
No class imbalance was observed, as both objects had equal representation.  

---

## Conclusion  
Fine-tuning with pretrained weights significantly improves object detection accuracy.  
YOLOv5 offers quicker inference while Faster R-CNN provides better precision.  
Scratch models are less effective, particularly with small datasets.  
