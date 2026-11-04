# Diabetic Retinopathy Detection Using Deep Learning

A computer-vision academic project that classifies retinal fundus images
into five diabetic-retinopathy severity categories using three CNN
architectures: ResNet50, DenseNet121 and DenseNet201. The ensemble
notebook combines the three model predictions using majority voting.

> **Disclaimer:** This repository is for educational and research
> purposes only. It is not a medical device and must not be used to
> diagnose, screen, or make treatment decisions. Clinical assessment
> must be performed by qualified healthcare professionals.

## Project overview

Diabetic retinopathy (DR) is an eye condition associated with diabetes.
This project explores image classification techniques for identifying DR
severity from retinal fundus photographs.

The notebooks work with the APTOS 2019 Blindness Detection-style data
structure (`train.csv`, `test.csv`, `train_images/`, and
`test_images/`). The dataset itself is not included in this repository.

## Severity classes

The notebooks use five classes:

    Label Class
  ------- ------------------
        0 No DR
        1 Mild
        2 Moderate
        3 Severe
        4 Proliferative DR

## Models

-   **ResNet50** --- individual model implementation.
-   **DenseNet121** --- individual model implementation.
-   **DenseNet201** --- individual model implementation.
-   **Ensemble** --- collects predictions from the three models and
    applies majority voting.

## Workflow covered in the notebooks

1.  Load the image labels and inspect the class distribution.
2.  Explore and visualize retinal fundus images.
3.  Resize images and apply preprocessing and augmentation.
4.  Prepare training, validation and test data loaders / class folders.
5.  Train or evaluate the individual CNN models.
6.  Load the trained model weights.
7.  Compare model predictions and calculate evaluation metrics.
8.  Combine predictions using majority voting.

The code uses image resizing and normalization based on ImageNet channel
statistics. Training augmentation includes random horizontal flipping in
the notebook pipeline.

## Repository contents

  ---------------------------------------------------------------------------
  File                                    Purpose
  --------------------------------------- -----------------------------------
  `Resnet50_github_clean.ipynb`           ResNet50 notebook

  `densenet121_github_clean.ipynb`        DenseNet121 notebook

  `DenseNet201_github_clean.ipynb`        DenseNet201 notebook

  `ensemble-methods_github_clean.ipynb`   Three-model majority-voting
                                          ensemble
  ---------------------------------------------------------------------------

## Tools and libraries

-   Python
-   PyTorch and Torchvision
-   NumPy and Pandas
-   OpenCV and Pillow
-   scikit-learn
-   Matplotlib and Seaborn
-   scikit-image
-   tqdm

## Dataset setup

The dataset is not redistributed here. Obtain it from its official
source or competition page and follow its terms of use.

The notebooks currently contain Google Colab / Google Drive paths such
as:

``` text
/content/drive/MyDrive/aptos2019-blindness-detection/
```

Before running the notebooks, update these paths to match your own
dataset location. The expected data layout is broadly:

``` text
aptos2019-blindness-detection/
├── train.csv
├── test.csv
├── train_images/
└── test_images/
```

The CSV files are expected to contain image identifiers and, for
labelled training data, a `diagnosis` column.

## Running the notebooks

1.  Open the required notebook in Google Colab or Jupyter.
2.  Install the required Python libraries in your environment.
3.  Download and arrange the dataset as described above.
4.  Update the dataset paths in the notebook.
5.  Run the preprocessing and model-specific cells.
6.  For the ensemble notebook, provide the trained weights for all three
    models and update the weight-file paths.

**Important:** The ensemble notebook expects trained checkpoint files
for ResNet50, DenseNet121 and DenseNet201. Those model-weight files are
not included in this repository. The notebook will not run end-to-end
until compatible checkpoints are supplied and their paths are updated.

## Evaluation

The notebooks include evaluation code using classification metrics such
as accuracy, precision, recall, F1-score and Cohen's kappa, as well as
confusion-matrix visualization in the model evaluation workflow.

Only report numerical results in your project presentation or resume if
they are reproduced from your own saved evaluation outputs and test
setup.

## Notes and limitations

-   Dataset files and trained model checkpoints are not included.
-   Google Drive paths must be changed for another environment.
-   Results depend on the dataset split, preprocessing, training
    configuration and model checkpoints used.
-   This repository documents an academic prototype, not a clinically
    validated diagnostic system.

## Author

**Mayur Maligi**

-   GitHub: https://github.com/mayurmaligi-sketch
-   LinkedIn: https://www.linkedin.com/in/mayur-maligi-6221812b6/
