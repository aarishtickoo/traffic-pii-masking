
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


  