# Drone vs Bird Classification — Custom CNN

Binary image classification that distinguishes **drones** from **birds** in aerial imagery, using a **from-scratch CNN** (no transfer learning backbone).

**Dataset:** [Drone vs Bird](https://www.kaggle.com/datasets/muhammadsaoodsarwar/drone-vs-bird) on Kaggle.

## Highlights

| Item | Detail |
|------|--------|
| Model | Custom CNN (4 conv blocks: 32→64→128→256) |
| Input size | 128×128×3 |
| Classes | Bird, Drone |
| Design | Conv2D → BatchNorm → ReLU (×2) → MaxPool → Dropout; GAP + Dense; sigmoid output |
| Parameters | ~1.28M total |

## Results (test set)

| Metric | Score |
|--------|------:|
| Accuracy | **95.26%** |
| Precision | 95.25% |
| Recall | 95.26% |
| F1-Score | **95.25%** |

Trained for 42 epochs with early stopping / best-weights checkpointing.

## Tech stack

- Python, TensorFlow / Keras
- scikit-learn (classification report, confusion matrix)
- Matplotlib / Seaborn
- kagglehub
- Google Colab (GPU recommended)

## How to run

1. Open [`BIM430_DroneVsBird_CustomCNN.ipynb`](BIM430_DroneVsBird_CustomCNN.ipynb) in [Google Colab](https://colab.research.google.com) or Jupyter.
2. Runtime → Change runtime type → **GPU**.
3. Run all cells in order.

```bash
pip install -r requirements.txt
```

The notebook downloads the Kaggle dataset at runtime. Large weights and raw images are gitignored.

## Project structure

```text
drone-vs-bird/
├── README.md
├── requirements.txt
├── .gitignore
└── BIM430_DroneVsBird_CustomCNN.ipynb
```

## License

Educational / portfolio project (BIM 430 style coursework). Dataset license follows the Kaggle source page.
