# Traffic PII Masking

A computer vision project for automated detection and masking
of personally identifiable information in traffic images.

## Objective

Develop an end-to-end licence plate detection and anonymization
pipeline using the BDD100K dataset, custom manual annotations,
transfer learning and YOLO object detection.

## Proof of Concept

- 50 manually reviewed and annotated traffic images
- 35 training, 5 validation and 10 test images
- 58 annotated licence plate instances
- Metadata-assisted image sampling
- Interactive dataset curation using ipywidgets
- Self-hosted CVAT for bounding box annotation

## Technology Stack

- Python
- NumPy
- Pandas
- Pillow
- Matplotlib
- OpenCV
- Jupyter
- CVAT
- Docker
- PyTorch
- Ultralytics YOLO11

## Project Status

- [x] Dataset exploration
- [x] Metadata-assisted sampling
- [x] Interactive dataset curation
- [x] Manual annotation
- [x] YOLO dataset export
- [x] Bounding box visualization
- [x] Initial YOLO11n proof of concept
- [x] Dataset v1 sampling/review workflow prepared
- [ ] Review and validate the 200-image Dataset v1 selection
- [ ] Annotate Dataset v1 licence plates
- [ ] Train the Dataset v1 model
- [ ] Model evaluation
- [ ] Automated licence plate masking
- [ ] Large-scale batch inference

## Dataset v1 Preparation

`notebooks/03_dataset_v1_sampling.ipynb` prepares an improved
200-image dataset with 160 train, 20 validation, and 20 test
images. It preserves official BDD100K split boundaries, uses
reproducible metadata-assisted candidate generation, caches
CPU-only YOLO11n vehicle statistics for the unannotated test
split, and persists manual review decisions after every action.

Generated sampling artifacts are kept under `data/dataset_v1/`.
The notebook does not launch expensive inference or the review
widget automatically. Dataset v1 training will begin only after
selection, validation, and licence plate annotation are complete.

## Dataset

BDD100K. Raw images are not distributed with this repository.
