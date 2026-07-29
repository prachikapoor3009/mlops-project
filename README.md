# mlops-project

This repository contains the code and configuration for the MLOps project.

## Screenshot

![Training summary screenshot](image.png)

## GitHub Actions CI

The `ci.yml` workflow under `.github/workflows/` runs on every push and pull request to the `main` branch.

It does the following:

- checks out the repository
- sets up Python for both `3.11` and `3.12` using a matrix strategy
- upgrades `pip`, `setuptools`, and `wheel`
- installs dependencies from `requirements.txt`
- runs `python train.py` to train and save the model
- lists the `artifacts` folder contents for debugging
- uploads the `artifacts` folder as a workflow artifact named `model-artifacts-<python-version>-<run_id>`

This ensures the model training pipeline can be validated automatically on supported Python versions.

