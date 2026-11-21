# GOHAN — Gender Classification from Offline Handwritten Signatures

Deep learning classification of a writer's gender from offline (scanned) handwritten signatures, using a VGG16 convolutional neural network. Implemented as Jupyter notebooks.

This repository accompanies the paper and the public dataset below.

## Dataset

**Offline Handwritten Signature Database based on Gender Annotation** — publicly available on Mendeley Data:

- DOI: [10.17632/22wgmdppxz.2](https://data.mendeley.com/datasets/22wgmdppxz/2)

Download the dataset and place it in a `data/` folder at the repository root before running the notebooks.

## Method

1. **Preprocessing** — signature images are cleaned, resized, and normalized for network input (grayscale conversion, background removal, resizing to the VGG16 input size).
2. **Model** — VGG16 CNN (transfer learning), fine-tuned on the signature dataset for binary gender classification.
3. **Training & evaluation** — train/validation/test split; performance measured with accuracy and a confusion matrix. Full experimental details are in the accompanying publication.

## Results

<!-- Replace the placeholders below with the values reported in your paper. -->
| Metric | Value |
|---|---|
| Accuracy | _TODO: fill in from paper_ |
| Precision | _TODO: fill in from paper_ |
| Recall | _TODO: fill in from paper_ |
| F1-score | _TODO: fill in from paper_ |

<!-- Paste the confusion matrix from your paper here (image or table). -->

## Requirements

```txt
# requirements.txt
tensorflow
keras
numpy
pandas
opencv-python
scikit-learn
matplotlib
jupyter
```

Install with:

```bash
pip install -r requirements.txt
```

## How to run

```bash
git clone https://github.com/SathishKumar2425/GOHAN.git
cd GOHAN
pip install -r requirements.txt
jupyter notebook
```

Then open the notebooks in order, update the dataset path to point at your local `data/` folder, and run all cells.

## License

MIT — see `LICENSE`.

<!-- If you agree with MIT, create the LICENSE file: GitHub repo page → Add file → Create new file → name it LICENSE → choose the MIT template. -->

## Suggested GitHub topics

`deep-learning` `cnn` `vgg16` `signature-verification` `biometrics` `gender-classification` `image-classification` `tensorflow` `keras` `computer-vision`

<!-- Add these on the repo page: gear icon next to "About" → Topics. -->
