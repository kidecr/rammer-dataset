# Rammer Pit LiDAR Point Cloud Dataset

[中文版](https://github.com/kidecr/rammer-dataset/blob/main/README_zh.md) | [English](https://github.com/kidecr/rammer-dataset/blob/main/README.md)

**Version:** 1.0

## Introduction

This is a publicly available 3D point cloud dataset specifically collected and constructed for the study of rammer pits in Dynamic Compaction (DC) engineering projects. The dataset aims to support and advance research in LiDAR-based automated settlement measurement, rammer pit detection, and related point cloud processing tasks. It is released alongside the paper *LiDAR-Based Auto-Measurement for Rammer Settlement*, in which key algorithms — including Two-Stage RANSAC Ground Fitting (TS-RGF) and Elevation-Constrained Pit Clustering (ECPC) — were developed and validated using this dataset.

## Dataset Composition

The dataset comprises LiDAR point cloud sequences captured from three distinct geographical locations and operational scenarios, designed to evaluate algorithm robustness under varying geological and environmental conditions:

1. **Xi'an, Shaanxi — Simulated Data** (`陕西西安/`)
   - **Description:** Artificially excavated pits simulating rammer impacts.
   - **Count:** 39 data sequences across three collection dates (2024.10.13, 2024.10.25, 2024.12.14).
   - **Features:** Systematic variation in pit depth and diameter, enabling preliminary algorithm validation under controlled, low-vibration conditions.

2. **Luoyang, Henan — Field Data (Per-Drop Recording)** (`河南洛阳/`)
   - **Description:** Real-world rammer pit data captured at active construction sites.
   - **Count:** 14 sequences, collected from 2 distinct rammer pits (Pit 1: 8 drops, Pit 2: 6 drops).
   - **Features:** Each drop (from hammer descent to lift) is recorded as a separate `.lvx` file.

3. **Zhongwei, Ningxia — Field Data (Full-Cycle Recording)** (`宁夏中卫/`)
   - **Description:** Real-world rammer pit data captured at active construction sites.
   - **Count:** 50 sequences from 10 distinct rammer pits.
   - **Features:** Each recording captures the complete dynamic compaction cycle from initiation to completion. **This subset served as the primary experimental validation data in the associated paper.**

## Data Content

- Each subset includes multi-drop point cloud sequences for multiple rammer pits.
- All point cloud data are accompanied by manually measured **ground truth** values, including pit depth and settlement amount, enabling quantitative performance evaluation of algorithms.
- Data were acquired using a **Livox Mid-70 LiDAR sensor**, mounted 5–10 meters above ground on a crane boom.
- Coordinate system: Right-handed, with **X-axis aligned to sensor forward direction**, and **Z-axis vertically upward** (perpendicular to X in the vertical plane).
- A co-located gyroscope (in the same coordinate frame) provided **initial Euler angle measurements** at the start of each recording to assist in coordinate alignment.

## File Format

- Raw point cloud data are stored in **`.lvx`** format — Livox's proprietary data format.
- To view and process `.lvx` files, please use **Livox Viewer** software.
  - Download: [Livox Viewer](https://www.livoxtech.com/cn/downloads)
- Ground truth is provided in **`.xlsx`** (Excel) format in each subdirectory.

## Data Download

Due to the large file size of the dataset, it is released via GitHub Releases. Please download from the following link:

**[Download Rammer Pit LiDAR Point Cloud Dataset v1.0](https://github.com/kidecr/rammer-dataset/releases/tag/dataset)**

You can also clone this repository (which contains only the README files):

```bash
git clone https://github.com/kidecr/rammer-dataset.git
```

### Dataset Structure
```
rammer-dataset/
├── 宁夏中卫/            # Zhongwei, Ningxia (Field Data - Full-Cycle)
│   ├── 1号坑5锤.lvx
│   ├── 2号坑1锤.lvx
│   └── ...
├── 河南洛阳/            # Luoyang, Henan (Field Data - Per-Drop)
│   ├── 强夯1号坑第一锤.lvx
│   ├── 强夯1号坑第二锤.lvx
│   └── ...
└── 陕西西安/            # Xi'an, Shaanxi (Simulated Data)
    ├── 2024.10.13/
    ├── 2024.10.25/
    └── 2024.12.14/
```

## License

This dataset is released under the **MIT License**.

## Citation

If you use this dataset in your research or publications, please cite the following paper:

```bibtex
@article{wang2024lidar,
  title={LiDAR-Based Auto-Measurement for Rammer Settlement},
  author={Wang, M. and others},
  journal={Preprint submitted to Elsevier},
  year={2024},
  url={https://github.com/kidecr/rammer-dataset}
}
```

## Contact

For questions or issues related to this dataset, please open an issue on GitHub or contact the authors.
