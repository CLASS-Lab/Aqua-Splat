# Aqua-Splat: Physically-Informed Sonar-Camera Gaussian Splatting for Underwater 3D Reconstruction

**Contact:** 25B965004@hit.edu.cn

The code is currently under maintenance. For any questions about the code or repository, please contact this email directly.

This repository contains the implementation of **Aqua-Splat**, a physically-informed Gaussian Splatting framework for underwater 3D reconstruction and novel view synthesis using both optical camera images and Forward-Looking Sonar (FLS) images.

Aqua-Splat extends 3D Gaussian Splatting to underwater acoustic-optic reconstruction by incorporating sonar image formation physics into the Gaussian rendering and optimization process.

---

## Overview

Underwater 3D reconstruction is challenging for camera-only methods because optical images are often affected by light absorption, backscattering, blur, and color distortion. Forward-Looking Sonar is more robust in degraded underwater environments, but its imaging process is fundamentally different from optical cameras.

Aqua-Splat combines the complementary advantages of camera and sonar sensors:

- Camera images provide high-resolution texture and appearance information.
- FLS sonar images provide robust geometric and structural cues.
- A shared 3D Gaussian scene representation is optimized using both modalities.

---

## Method

Aqua-Splat represents the underwater scene with 3D Gaussians and jointly optimizes them using camera and sonar supervision.

The main pipeline includes:

1. Initializing a 3D Gaussian scene representation.
2. Rendering optical images using the standard Gaussian Splatting pipeline.
3. Transforming Gaussians from Cartesian space to the sonar polar coordinate system.
4. Rendering sonar images according to the physical imaging process of FLS.
5. Optimizing the Gaussian scene using both camera loss and sonar loss.
6. Applying sonar-guided densification to improve geometric reconstruction.

---
## Installation

The installation follows the original 3D Gaussian Splatting setup. This repository uses the same basic environment configuration and CUDA extension dependencies as the official 3DGS implementation.

Clone the repository with submodules:

```bash
git clone https://github.com/CLASS-Lab/Aqua-Splat --recursive
cd Aqua-Splat
```

The core dependencies are inherited from the original 3D Gaussian Splatting codebase, including PyTorch, CUDA extensions, diff-gaussian-rasterization, and simple-knn.

After the environment is created, the repository can be used in the same way as the original 3DGS codebase, with Aqua-Splat adding sonar-camera reconstruction modules on top of it.

---

## Citation

If you find this work useful, please cite:

```bibtex
@ARTICLE{11184160,
  author={Ling, Zijie and Feng, Yunxuan and Meng, Ao and Xiao, Renxiang and Pan, Shu and Lu, Wenjie and Hu, Liang},
  journal={IEEE Robotics and Automation Letters}, 
  title={Aqua-Splat: Physically-Informed Sonar-Camera Gaussian Splatting for Underwater 3D Reconstruction}, 
  year={2025},
  volume={10},
  number={11},
  pages={11896-11903},
  keywords={Sonar;Three-dimensional displays;Image reconstruction;Rendering (computer graphics);Cameras;Visualization;Geometry;Sonar measurements;Accuracy;Optical sensors;Gaussian splatting;acoustic-optic vision;sensor fusion},
  doi={10.1109/LRA.2025.3615528}}
