# Project Instructions

## Project Overview

This is a computer vision portfolio project focused on
automated licence plate detection and anonymization in
traffic images using the BDD100K dataset.

## Development Approach

- Develop the project incrementally, one milestone at a time.
- Do not implement the entire project in a single step.
- Explain important technical and architectural decisions.
- Prioritize learning and understanding over rapid code generation.
- Avoid unnecessary abstractions and overengineering.
- Consult PROJECT_PLAN.md before implementing new features.
- Do not introduce major architectural changes without discussion.

## Coding Standards

- Use Python.
- Use pathlib for filesystem operations.
- Write modular, readable and maintainable code.
- Use type hints where appropriate.
- Avoid hardcoded absolute paths.
- Use reproducible random seeds.
- Keep configuration separate from implementation.
- Handle errors explicitly.

## Machine Learning Standards

- Preserve the original BDD100K train/val/test split.
- Prevent data leakage between dataset splits.
- Never use test data for training or hyperparameter tuning.
- Prioritize recall for licence plate detection.
- Track experiments and document their results.
- Perform error analysis before increasing model complexity.

## Data Management

- Do not commit raw images or large model weights to Git.
- Do not publish identifiable licence plates.
- Verify dataset licensing before redistributing images.
- Preserve original images locally.
- Save anonymized images separately.

## Current Priority

Dataset exploration, sampling and annotation.

Do not begin model training until the dataset preparation
milestone is complete.
