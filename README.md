# GOHAN: Gender Classification from Offline Handwritten Signatures

Deep learning classification of a writer's gender from offline (scanned) handwritten signatures, using a VGG16 convolutional neural network (transfer learning). Implemented as Jupyter notebooks in TensorFlow/Keras.

This repository accompanies the published paper and the public dataset below.

## Dataset

**Offline Handwritten Signature Database based on Gender Annotation**, publicly available on Mendeley Data:

- DOI: [10.17632/22wgmdppxz.2](https://data.mendeley.com/datasets/22wgmdppxz/2)

Download the dataset and place it in a `data/` folder at the repository root before running the notebooks.

## Method

1. **Preprocessing**: signature images are cleaned, resized, and normalized for network input (grayscale conversion, background removal, resizing to the VGG16 input size).
2. **Model**: VGG16 CNN (transfer learning), fine-tuned on the signature dataset for binary gender classification.
3. **Training and evaluation**: train/validation/test split; performance measured with accuracy and a confusion matrix. Full experimental details are in the accompanying publication.

Note: the accompanying paper extracts AlexNet CNN features and classifies them with KNN, SVM and an ensemble classifier; this repository's notebook instead uses a VGG16 transfer-learning model.

## Results

Results reported in the accompanying paper (Kumar, Gornale & Siddalingappa, "Gender Classification from Behavioural Biometric Data using Convolutional Neural Network", ACVAIT 2022, [doi:10.2991/978-94-6463-196-8_49](https://doi.org/10.2991/978-94-6463-196-8_49)), Table 4 and Fig. 6. The dataset comprises 4,790 signatures from 479 writers (250 male, 229 female), split 70:30 for training and testing. CNN features were classified with KNN, SVM and an ensemble classifier:

| Classifier | Accuracy |
| --- | --- |
| CNN + SVM | 84.40% |
| CNN + KNN (k = 3) | 94.20% |
| CNN + Ensemble (bagging, 30 learners) | 95.40% |

The paper defines precision, recall and F-score (Eqs. 8-11) but reports numeric accuracy only, so those values are not listed here.

## Repository contents

- `DataSplitSubfolder.ipynb`: splits the dataset folders into train, validation and test sets (10% test, 20% validation by default).
- `SagarSignVGG16.ipynb`: VGG16 feature extractor with a trained classifier head, evaluation metrics and confusion matrix.
- `requirements.txt`: Python dependencies.

## Setup

```bash
git clone https://github.com/SathishKumar2425/GOHAN.git
cd GOHAN
pip install -r requirements.txt
jupyter notebook
```

Open the notebooks in the order listed above, update the dataset path to point at your local `data/` folder, and run all cells.

## License

MIT. See [LICENSE](LICENSE).
