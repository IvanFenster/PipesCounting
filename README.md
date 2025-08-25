# Pipes Counting 

This repository contains notebooks, and trained weights for our project on detecting and counting steel profiles in photos using a YOLO-based model.

The model recognizes and counts four profile types:

* Round pipes
* Square pipes
* Channel profiles (self-annotated)
* Angle profiles (self-annotated)

---

## Repository Structure

```
.
├── yolo_training.ipynb    # Train YOLO on the prepared dataset
├── main.ipynb             # Run inference and get counts per class
├── evaluate.ipynb         # Evaluate the model and inspect results
├── final_weights.pt       # Trained weights (ready to use)
├── example.jpg            # Example image for a quick test
└── requirements.txt
```

---

## Installation

```bash
git clone https://github.com/<your-username>/pipe-counting-yolo.git
cd pipe-counting-yolo
pip install -r requirements.txt
```

Notes:

* Python 3.9+ is recommended.
* The notebooks assume the `ultralytics` package (YOLO) and `opencv-python` are installed, along with standard scientific Python libraries.

---

## Usage (Notebooks)

1. **Train the model** — open `yolo_training.ipynb`

   * Set the path to your dataset YAML (with classes: `circle`, `square`, `channel`, `angle`).
   * Configure training parameters (epochs, image size, etc.) and run the cells.

2. **Run inference** — open `main.ipynb`

   * Set `weights` to `final_weights.pt` (or your own) and provide a path to an image or folder (e.g., `example.jpg`).
   * Run the cells to visualize detections and print the counts per class.

3. **Evaluate** — open `evaluate.ipynb`

   * Point to your validation set and weights.
   * Run the cells to compute metrics and review qualitative results.

---

## Data Notes

* Datasets combine manually annotated images with augmented and synthetic samples.
* Ensure your dataset YAML lists the classes in the same order used during training:

  ```yaml
  names: [circle, square, channel, angle]
  ```

---

## Weights

* `final_weights.pt` is provided for quick testing in `main.ipynb`.
* You can retrain the model with `yolo_training.ipynb` and save your own weights.

---

## Team

Project developed by Team 42:
- Ivan Fenster
- Alexander Povarov
- Konstantin Spirin
- Ignat Sukhanovsky
- Andrey Bushin
