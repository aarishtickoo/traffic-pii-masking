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

## Dataset v1 Review Budget

Select 200 images while preserving the official BDD100K
split boundaries:

- Training: 160 images
- Validation: 20 images
- Testing: 20 images

The target is plates containing human-readable registration
information. Each split includes clear readable, challenging
but readable, and negative images. Candidate generation is
metadata-assisted and reproducible; final inclusion is based
on manual review.

## Dataset v1 Sampling Categories

1. Clear readable: registration information is human-readable.
2. Challenging but readable: the plate is harder to inspect but
   registration information remains human-readable.
3. Negative: no plate with human-readable registration
   information is present.

Multiple readable plates are allowed but are not a separate
sampling category. Detailed annotation rules will be finalized
before annotation begins.

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
- [x] Analyze image dimensions
- [x] Explore available dataset metadata
- [x] Complete a 50-image end-to-end proof of concept
- [x] Prepare the Dataset v1 candidate-generation and review notebook
- [ ] Generate Dataset v1 candidate pools (approximately 800/100/100)
- [ ] Review candidates against the 160/20/20 split quotas
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

Repository setup, dataset exploration, and the initial
50-image YOLO11n proof of concept are complete. The BDD100K
archive remains under `data/raw/bdd100k/` with its original
train, validation, and test splits preserved.

`notebooks/03_dataset_v1_sampling.ipynb` now defines the next
dataset-preparation stage. The immediate next step is to cache
test-split vehicle statistics, generate candidate pools, and
manually review images. Model training remains blocked until
the 200-image selection and licence plate annotation milestone
is complete.
