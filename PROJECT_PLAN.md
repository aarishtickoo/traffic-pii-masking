# Traffic PII Masking

## Objective

Build an end-to-end computer vision pipeline that learns
to detect licence plates from a small manually annotated
subset of traffic images and automatically anonymizes
licence plates across thousands of unlabelled images.

The project is intended to demonstrate practical computer
vision and machine learning engineering skills.

## Dataset

- BDD100K
- 100,000 traffic images
- Original train/val/test split: 70/10/20
- Preserve the original dataset splits.

### Verified Local Structure

The Kaggle archive was inspected and extracted without
changing its internal layout:

```text
data/raw/bdd100k/
|-- train/
|   |-- annotations/
|   |   `-- bdd100k_labels_images_train.json
|   `-- images/                     # 70,000 JPG images
|-- val/
|   |-- annotations/
|   |   `-- bdd100k_labels_images_val.json
|   `-- images/                     # 10,000 JPG images
`-- test/                            # 20,000 JPG images
```

The test split is intentionally asymmetric: its images are
stored directly inside `test/`, and the archive contains no
test annotation JSON. The archive contains 100,002 files and
has an uncompressed size of 7,451,243,332 bytes (6.94 GiB).
The original ZIP archive is retained outside the repository.

## Initial Scope

- Licence plate detection only.
- Face detection is a potential future extension.
- Static images, not video.
- Batch inference rather than real-time inference.

## Annotation Budget

Initially annotate 200 images manually:

- Training: 140 images
- Validation: 20 images
- Testing: 40 images

Use deliberate sampling for training and random sampling
for validation and testing.

## Image Categories

1. Negative: No visible licence plates.
2. Easy: Clear and easily distinguishable licence plates.
3. Difficult: Small, blurred, angled or partially occluded
   but identifiable licence plates.
4. Ambiguous: Potential plates that cannot confidently
   be identified.

Annotate every confidently identifiable licence plate,
regardless of whether its characters are readable.

## Technology Stack

- Python
- PyTorch
- Ultralytics YOLO11
- OpenCV
- CVAT
- Pandas
- NumPy
- Matplotlib
- MLflow (later)
- SAHI (later)
- Docker (later)

## Milestone 1: Dataset Preparation

- [x] Define project scope
- [x] Select BDD100K dataset
- [x] Preliminary visual inspection
- [x] Initialize Git repository
- [x] Set up project-specific Python 3.12 environment
- [x] Configure the VS Code interpreter
- [x] Install initial exploration dependencies
- [x] Download and safely extract the BDD100K archive
- [x] Verify dataset structure, splits and image counts
- [ ] Analyze image dimensions
- [ ] Explore available dataset metadata
- [ ] Sample 500 training images
- [ ] Categorize sampled images
- [ ] Finalize annotation guidelines
- [ ] Select 200 images for annotation
- [ ] Set up CVAT
- [ ] Annotate licence plates
- [ ] Export annotations in YOLO format

## Milestone 2: Baseline Model

- [ ] Fine-tune pretrained YOLO11n
- [ ] Evaluate precision, recall and mAP
- [ ] Perform visual error analysis
- [ ] Implement licence plate masking
- [ ] Generate initial anonymized images

## Milestone 3: Model Optimization

- [ ] Data efficiency experiments
- [ ] Compare different training dataset sizes
- [ ] Compare inference resolutions
- [ ] Investigate SAHI for small object detection
- [ ] Experiment with active learning
- [ ] Optimize detection confidence thresholds

## Milestone 4: Batch Inference

- [ ] Process 10,000 unlabelled images
- [ ] Generate anonymized images
- [ ] Record inference metadata
- [ ] Measure inference throughput
- [ ] Audit residual PII leakage

## Milestone 5: Portfolio Packaging

- [ ] Document methodology
- [ ] Publish experimental results
- [ ] Create visual demonstrations
- [ ] Build reproducible inference pipeline
- [ ] Prepare GitHub README
- [ ] Dockerize application

## Current Status

Repository and Python environment setup are complete. The
BDD100K archive has been extracted to `data/raw/bdd100k/`,
and its original train, validation and test splits have been
preserved and verified.

The initial dataset exploration notebook exists but contains
no exploration logic yet. The immediate next step is to
analyze image dimensions and the available BDD100K metadata.
