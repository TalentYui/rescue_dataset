# OFRA-YOLO-Dataset

This repository hosts the dataset used in the **OFRA-YOLO** paper, a general-purpose object detection method built on top of the YOLO family of detectors.

> **Note:** The actual data files are hosted on **Baidu Netdisk** (a Chinese cloud-storage service) and are **not** stored in this repository. See the [Download](#download) section below.

---

## Overview

- **Task:** Generic object detection
- **Detector:** OFRA-YOLO (based on the YOLO architecture)
- **Annotation format:** YOLO format (one `.txt` file per image)
- **Number of images:** ~[1,000 – 10,000] *(please fill in the exact count)*
- **Number of classes:** [N] *(please fill in)*

The dataset is intended for reproducing the results reported in the OFRA-YOLO paper and for benchmarking object detection models.

---

## Download

The dataset is shared via Baidu Netdisk. Please use the following link and extraction code:

| Item            | Value                                                       |
| --------------- | ----------------------------------------------------------- |
| **Link**        | https://pan.baidu.com/s/1hAfCI6pNcBO7DqStinvXiQ             |
| **Extraction code** | `1243`                                                  |

> **Tips for non-Chinese users:**
> - Baidu Netdisk requires a (free) Baidu account to download.
> - Large files typically require the official Baidu Netdisk desktop client or mobile app, and download speed may be throttled for free accounts.
> - If the link expires or becomes invalid, please open an issue in this repository.

---

## Dataset Contents

The dataset contains:

- **Images:** raw images organized by class directory.
- **Labels:** YOLO-format annotation files (`.txt`), one per image.

```
OFRA-YOLO-Dataset/
├── <class_1>/
│   ├── image_001.jpg
│   ├── image_001.txt
│   └── ...
├── <class_2>/
│   ├── image_001.jpg
│   ├── image_001.txt
│   └── ...
└── ...
```

> If the exact folder layout differs from the above, please update this section to reflect the real structure.

---

## Annotation Format (YOLO)

Each image is paired with a plain-text `.txt` file of the same name. Every line in the file describes one object:

```
<class_id> <x_center> <y_center> <width> <height>
```

- `<class_id>` — integer, the zero-based class index.
- `<x_center>`, `<y_center>` — the center of the bounding box.
- `<width>`, `<height>` — the size of the bounding box.
- All four coordinates are **normalized** to `[0, 1]` relative to the image width and height.

### Example

```
0 0.518750 0.405000 0.262500 0.410000
1 0.231250 0.550000 0.125000 0.230000
```

---

## Class List

| Class ID | Name |
| -------- | ---- |
| 0        | [class name] |
| 1        | [class name] |
| ...      | ... |

> *(Please fill in the full class list.)*

---

## Usage

You can load this dataset directly with any YOLO-compatible training pipeline (e.g., [Ultralytics YOLOv8/YOLO11](https://github.com/ultralytics/ultralytics)) by providing a `data.yaml` similar to:

```yaml
path: /path/to/OFRA-YOLO-Dataset
train: images/train   # adjust to your actual split
val: images/val       # adjust to your actual split
test: images/test     # optional

names:
  0: [class_0_name]
  1: [class_1_name]
  # ...
```

> Adjust the `train`/`val`/`test` paths and `names` to match the real folder layout and class list.

---

## Citation

If you use this dataset in your research, please cite the OFRA-YOLO paper:

```
[TODO: add the full citation / BibTeX entry for the OFRA-YOLO paper]
```

---

## License

> *(Please specify the license under which this dataset is released, e.g., CC BY 4.0, MIT, or a custom agreement.)*

---

## Contact

For questions or issues regarding the dataset, please open an [issue](../../issues) in this repository.
