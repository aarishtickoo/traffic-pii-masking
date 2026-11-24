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
- PyTorch (planned)
- Ultralytics YOLO (planned)

## Project Status

- [x] Dataset exploration
- [x] Metadata-assisted sampling
- [x] Interactive dataset curation
- [x] Manual annotation
- [x] YOLO dataset export
- [x] Bounding box visualization
- [ ] Dataset validation
- [ ] Model training
- [ ] Model evaluation
- [ ] Automated licence plate masking
- [ ] Large-scale batch inference

## Dataset

BDD100K. Raw images are not distributed with this repository.