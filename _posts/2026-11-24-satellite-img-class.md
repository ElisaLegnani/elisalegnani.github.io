---
layout: post
title:  "Project on satellite image classification"
date:   2026-11-24
categories: website
---

![Web app classifying a satellite image](https://raw.githubusercontent.com/ElisaLegnani/satellite-image-classifier/main/docs/images/app_screenshot.png)

[Satellite Image Classification](https://github.com/ElisaLegnani/satellite-image-classifier) is a small machine-learning application that classifies satellite image patches into 10 land-cover categories, such as forest, river or highway.

I built it mostly to refresh my skills with the tooling around a model, from experiment tracking to deployment and CI, in a short, self-contained project. The model is deliberately simple; the point was the workflow around it.

## What it does

You upload a satellite image in a web app and get back the predicted land-cover class together with the confidence for each class. Under the hood, a PyTorch CNN trained on the [EuroSAT](https://github.com/phelber/EuroSAT) RGB dataset (27,000 Sentinel-2 patches, 64 x 64 pixels) does the prediction, served through a REST API.

## How it's built

- **PyTorch** for the CNN, with a 70/15/15 train/validation/test split
- **MLflow** to log parameters, metrics and artefacts, so I can compare runs instead of tracking them by hand
- **FastAPI** for the prediction API, with automatic docs, and **Streamlit** for the frontend
- **Docker Compose** to start the API and the frontend together with a single command
- **Pytest** and **Ruff** for tests and linting, run on every push with GitHub Actions

## Results

On the held-out test set the model reaches 80% accuracy and a macro F1-score of 0.79. Forest, Residential and SeaLake are the easiest classes (F1 ≥ 0.92). Highway is the hardest (F1 = 0.49), followed by River and PermanentCrop.

<img src="/assets/images/confusion_matrix_test.png" alt="Confusion matrix on the test set" width="500">

These are not state-of-the-art numbers, and that's fine for this project. Possible next steps are data augmentation, a pretrained backbone, or a larger and more recent training dataset.

The code is on [GitHub](https://github.com/ElisaLegnani/satellite-image-classifier), and the README has instructions to run the application.
