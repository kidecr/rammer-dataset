# 夯锤坑 LiDAR 点云数据集

[中文版](https://github.com/kidecr/rammer-dataset/blob/main/README_zh.md) | [English](https://github.com/kidecr/rammer-dataset/blob/main/README.md)

**版本:** 1.0

## 简介

本数据集是专门为强夯工程中夯坑深度研究而采集和构建的三维点云数据集。该数据集旨在支持和促进基于LiDAR的自动化夯沉量测量、夯坑检测等领域的研究。数据集随论文《LiDAR-Based Auto-Measurement for Rammer Settlement》一同发布，论文中提出的"两阶段RANSAC地面拟合"(TS-RGF)和"高程约束坑聚类"(ECPC)等算法均在此数据集上进行了验证。

## 数据集构成

本数据集包含来自三个不同地点和场景的点云数据，以评估算法在不同地质条件和操作环境下的适应性：

1. **西安, 陕西 — 模拟数据** (`陕西西安/`)
   - **描述:** 通过人工挖掘模拟夯锤冲击形成的坑洞。
   - **数量:** 39组数据，分三次采集（2024.10.13, 2024.10.25, 2024.12.14）。
   - **特点:** 坑洞的深度和直径经过系统性变化，用于在受控、低振动的理想条件下进行初步算法验证。

2. **洛阳, 河南 — 现场数据（逐锤记录）** (`河南洛阳/`)
   - **描述:** 来自真实施工现场的夯锤坑数据。
   - **数量:** 14组数据，采集自2个不同的夯点（Pit 1: 8次夯击, Pit 2: 6次夯击）。
   - **特点:** 每次夯击从夯锤下落至提起的过程均被单独记录为一个文件。

3. **中卫, 宁夏 — 现场数据（全周期记录）** (`宁夏中卫/`)
   - **描述:** 来自真实施工现场的夯锤坑数据。
   - **数量:** 50组数据，采集自10个不同的夯点。
   - **特点:** 每次记录都捕捉了从施工开始到完成的完整强夯循环。**此子集是论文中实验验证的主要数据来源。**

## 数据内容

- 每个子集均包含针对多个夯点、多次夯击的点云序列。
- 所有点云数据均配有通过人工测量获得的"真实值"(Ground Truth)，包括夯坑深度和夯沉量，可用于算法性能评估。
- 数据采集使用 **Livox Mid-70 LiDAR** 传感器，安装在距离地面5至10米的吊车臂上。
- 点云数据坐标系为右手坐标系：X轴为传感器正前方，Z轴垂直X轴向上。
- 数据采集过程中，同坐标系下的陀螺仪提供了测量开始时的角度偏转（欧拉角）测量值。

## 文件格式

- 原始点云数据格式为 **`.lvx`**。
- 此格式为Livox官方数据格式，需使用 **Livox Viewer** 软件进行查看和处理。
- 软件下载地址: [Livox Viewer](https://www.livoxtech.com/cn/downloads)
- 真实值数据存储在各子目录的 `.xlsx` 文件中，包含每次测量的手动测量深度、欧拉角等信息。

## 数据下载

由于数据集文件较大，现通过 GitHub Releases 发布。请通过以下链接下载：

**[下载夯锤坑 LiDAR 点云数据集 v1.0](https://github.com/kidecr/rammer-dataset/releases/tag/dataset)**

您也可以克隆此仓库（仅包含 README 文件）：

```bash
git clone https://github.com/kidecr/rammer-dataset.git
```

### 数据集结构
```
rammer-dataset/
├── 宁夏中卫/            # 中卫，宁夏（现场数据 - 全周期记录）
│   ├── 1号坑5锤.lvx
│   ├── 2号坑1锤.lvx
│   └── ...
├── 河南洛阳/            # 洛阳，河南（现场数据 - 逐锤记录）
│   ├── 强夯1号坑第一锤.lvx
│   ├── 强夯1号坑第二锤.lvx
│   └── ...
└── 陕西西安/            # 西安，陕西（模拟数据）
    ├── 2024.10.13/
    ├── 2024.10.25/
    └── 2024.12.14/
```

## 使用许可

本数据集遵循 **MIT** 许可协议。

## 引用方式

如果您在研究中使用了本数据集，请在您的出版物中引用以下文献：

```bibtex
@article{wang2024lidar,
  title={LiDAR-Based Auto-Measurement for Rammer Settlement},
  author={Wang, M. and others},
  journal={Preprint submitted to Elsevier},
  year={2024},
  url={https://github.com/kidecr/rammer-dataset}
}
```

## 联系方式

如有关于本数据集的问题或建议，请在 GitHub 上提交 Issue 或联系作者。
