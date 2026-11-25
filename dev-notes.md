
An RGB image is essentially a three-dimensional numerical array:
{Image shape} = (H, W, C) 
img[row, column, channel]
img[y, x, c]

Notice that Pillow reports dimensions as (width, height), whereas NumPy represents images as (height, width, channels).


| Representation | Convention | BDD100K image shape |
|---|---|---|
| NumPy / OpenCV | HWC | `(720, 1280, 3)` |
| PyTorch image tensor | CHW | `(3, 720, 1280)` |
| PyTorch image batch | BCHW | `(16, 3, 720, 1280)` |


(0,0) ──────────────────────────────► x
  │
  │
  │       (x1,y1)
  │          ┌────────────────┐
  │          │                │
  │          │     Vehicle    │
  │          │                │
  │          └────────────────┘
  │                        (x2,y2)
  │
  ▼
  y


  

## Dataset v1 sampling workflow

The initial 50-image proof of concept is complete. The next
experiment uses a separately reviewed 200-image dataset focused
on plates with human-readable registration information:

| Split | Clear | Challenging | Negative | Total |
|---|---:|---:|---:|---:|
| Train | 128 | 16 | 16 | 160 |
| Validation | 16 | 2 | 2 | 20 |
| Test | 16 | 2 | 2 | 20 |

`notebooks/03_dataset_v1_sampling.ipynb` contains the candidate
generation, cached test vehicle-statistics inference, persistent
ipywidgets review, validation, and image materialization steps.
The candidate pool and review records are append-preserving so
the pool can grow without discarding earlier manual decisions.

Do not begin Dataset v1 training until image review, annotation
guidelines, licence plate annotation, and export validation are
complete.
