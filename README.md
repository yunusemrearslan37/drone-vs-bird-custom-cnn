# Drone vs Bird Sınıflandırma — Özel CNN

Hava görüntülerinde **drone** ile **kuş** ayrımı yapan ikili görüntü sınıflandırma projesi. Model **sıfırdan tasarlanmış bir CNN** kullanır (transfer learning omurgası yok).

**Veri seti:** Kaggle [Drone vs Bird](https://www.kaggle.com/datasets/muhammadsaoodsarwar/drone-vs-bird)

## Öne çıkanlar

| Madde | Detay |
|------|--------|
| Model | Özel CNN (4 konvolüsyon bloğu: 32→64→128→256) |
| Giriş boyutu | 128×128×3 |
| Sınıflar | Bird, Drone |
| Mimari | Conv2D → BatchNorm → ReLU (×2) → MaxPool → Dropout; GAP + Dense; sigmoid çıkış |
| Parametre | ~1,28M toplam |

## Sonuçlar (test seti)

| Metrik | Skor |
|--------|------:|
| Accuracy | **95,26%** |
| Precision | 95,25% |
| Recall | 95,26% |
| F1-Score | **95,25%** |

Eğitim 42 epoch sürdü; early stopping ve en iyi ağırlıkların kaydı kullanıldı.

## Kullanılan teknolojiler

- Python, TensorFlow / Keras
- scikit-learn (classification report, confusion matrix)
- Matplotlib / Seaborn
- kagglehub
- Google Colab (GPU önerilir)

## Nasıl çalıştırılır?

1. [`BIM430_DroneVsBird_CustomCNN.ipynb`](BIM430_DroneVsBird_CustomCNN.ipynb) dosyasını [Google Colab](https://colab.research.google.com) veya Jupyter’da açın.
2. Runtime → Change runtime type → **GPU**.
3. Hücreleri sırayla çalıştırın.

```bash
pip install -r requirements.txt
```

Notebook, Kaggle veri setini çalışma sırasında indirir. Büyük model ağırlıkları ve ham görüntüler gitignore ile repoya alınmaz.

## Proje yapısı

```text
drone-vs-bird/
├── README.md
├── requirements.txt
├── .gitignore
└── BIM430_DroneVsBird_CustomCNN.ipynb
```

## Lisans

Eğitim / portföy amaçlı proje (BIM 430 tarzı ders çalışması). Veri seti lisansı Kaggle kaynak sayfasındaki koşullara tabidir.
