# YOLO Fine-Tuning for Cheating Detection

## Project Overview

This project demonstrates how to fine-tune the **YOLO v11** object detection algorithm to automatically identify suspicious actions—such as head tilts, phone usage, and abnormal eye movements—that may indicate cheating during online or offline examinations. The aim is to provide robust and reliable monitoring tools for educational institutions and proctoring systems.

## Dataset

- **Total Images:** ~2,700 annotated images
- **Classes:** 
  - `Cheat` (suspicious actions)
  - `Normal` (regular behavior)
- **Annotation Tool:** [Roboflow](https://roboflow.com/)
- **Data Splits:** Train / Validation / Test

Each image in the dataset is labeled with bounding boxes and class annotations, making it suitable for supervised learning using object detection algorithms.

## Approach

1. **Data Preparation**
   - Annotated images were exported from Roboflow in YOLO format.
   - The dataset was split into training, validation, and test sets for robust evaluation.

2. **Model Fine-Tuning**
   - **YOLO v11** was selected for its state-of-the-art speed and accuracy.
   - Transfer learning is applied using pretrained weights.
   - Hyperparameters can be adjusted to optimize detection performance.

3. **Training**
   - The model is trained to distinguish between cheating and normal behavior.
   - Augmentation techniques (e.g., rotation, scaling, flipping) may be used to improve generalization.

4. **Evaluation**
   - Performance metrics include mAP (mean Average Precision), precision, recall, and F1-score.
   - Visualization of bounding box predictions on sample test images.

5. **Deployment**
   - Export the trained model for use in real-time proctoring solutions or batch analysis.
   - Integration options for Python scripts, web apps, or mobile applications.

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/ajaygadge77/YOLO-fine-tuning-.git
cd YOLO-fine-tuning-
```

### 2. Prepare the Dataset

- Download and extract your annotated images and labels into the appropriate `data/` folder structure.
- Update `data.yaml` to reflect your dataset paths and class names.

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Train the Model

```bash
python train.py --img 640 --batch 16 --epochs 50 --data data.yaml --weights yolov11.pt
```

### 5. Evaluate and Visualize

```bash
python val.py --data data.yaml --weights runs/train/exp/weights/best.pt
```

### 6. Inference

```bash
python detect.py --weights runs/train/exp/weights/best.pt --source path/to/test/images
```

## Results

- **Sample Outputs:** Detection images showing bounding boxes for "Cheat" and "Normal" classes.
- **Performance Metrics:** mAP, precision, recall scores for validation and test sets.

## Applications

- Automated exam proctoring
- Classroom monitoring
- Online interview integrity
- Any scenario requiring behavioral analysis from video/image data

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- YOLO v11 authors
- [Roboflow](https://roboflow.com/)
- Open source contributors

---

**Contact:** [Ajay Gadge](https://github.com/ajaygadge77)
