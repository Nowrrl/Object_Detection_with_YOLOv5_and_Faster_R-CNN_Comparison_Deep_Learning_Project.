Object Detection with YOLOv5 and Faster R-CNN: A Comparative Study
Project Overview
This project aims to design and compare object detection models trained from scratch and using transfer learning. We applied YOLOv5 and Faster R-CNN on two everyday objects: Axe deodorant and Mouse. The goal was to evaluate the effects of augmentation and training strategies on detection accuracy.

Dataset
The dataset consists of:

Objects: Axe deodorant and Mouse

Images: 50 images (25+ per object) taken from various angles and distances

Resolution: 416x416 pixels (to match YOLOv5 input requirements)

Labeling Tool: LabelImg

Format: Pascal VOC (.xml)

Data Augmentation Techniques
To improve model generalization, the following augmentations were applied:

Flips: Horizontal and Vertical

Rotations: +45° and -45°

Brightness Adjustments: Increasing and Decreasing

Image Enhancements: Sharpening and Blurring

Color Adjustments: Hue and Saturation shifts

Model Training
Four models were trained:

YOLOv5 (Scratch) - 10 epochs

YOLOv5 (Fine-Tuned) - 10 epochs

Faster R-CNN (Scratch) - 15 epochs

Faster R-CNN (Fine-Tuned) - 15 epochs

Hyperparameters:

Batch size: 16

Learning rate: 0.005

Optimizer: SGD

Evaluation Metrics
The following metrics were used to evaluate model performance:

Precision

Recall

F1 Score

Model	Precision	Recall	F1 Score
YOLOv5 Fine-Tuned	~0.70	~0.80	~0.70
YOLOv5 Scratch	~0.00	~0.00	~0.00
Faster R-CNN Scratch	0.538	0.667	0.594
Faster R-CNN Fine-Tuned	0.636	0.667	0.651

Results and Observations
Fine-Tuned Models: Achieved better performance and higher accuracy.

YOLOv5 Fine-Tuned: Accurate detections, faster inference.

Faster R-CNN Fine-Tuned: Strong detection, slower inference.

Scratch Models: Performed poorly, highlighting the importance of transfer learning.

Visual Inference
YOLOv5 Fine-Tuned detected objects correctly.

Faster R-CNN Fine-Tuned showed accurate predictions with proper labeling.

Scratch models had inconsistent results, with YOLOv5 Scratch failing entirely.

Challenges
Lighting Inconsistencies: Mitigated using brightness and shadow augmentation.

Object Occlusion: Addressed by including multiple perspectives and rotations.

Class Imbalance: None observed as both objects had equal representation.

Conclusion
Fine-tuning using pretrained weights significantly enhances object detection accuracy. YOLOv5 provides quicker inference while Faster R-CNN delivers better precision. Scratch models require larger datasets and more training to achieve similar results.
