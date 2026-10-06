# Camera Calibration & 3D Point Cloud Reconstruction

A computer vision pipeline built in Python to perform geometric camera calibration using chessboard patterns and generate 3D point clouds from calibrated intrinsic and extrinsic camera parameters.

---

## 🛠️ Features

- **Camera Calibration (`calibration.py`):**
  - Automatic detection of internal chessboard corners (`cv2.findChessboardCorners`).
  - Sub-pixel coordinate refinement (`cv2.cornerSubPix`).
  - Computation of the camera intrinsic matrix, distortion coefficients, rotation vectors, and translation vectors.
  - Automatic parameter export to the `camera_params/` directory.

- **3D Processing & Reconstruction (`Projet.py`):**
  - Loads saved camera parameter matrices (`.npy`).
  - Image processing and 3D projection for point cloud extraction.
  - Export and management of 3D data within the `nuage_de_points/` directory.

---

## 📂 Repository Structure

```text
.
├── camera_params/      # Output directory for saved calibration parameters (.npy)
├── nuage_de_points/    # Output directory for generated 3D point cloud data
├── calibration.py      # Camera calibration script
├── Projet.py           # Main script for 3D processing and point cloud generation
└── README.md           # Project documentation
```

---

## 📋 Requirements & Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/3d-pointcloud-reconstruction.git](https://github.com/your-username/3d-pointcloud-reconstruction.git)
   cd 3d-pointcloud-reconstruction
   ```

2. **Install dependencies:**
   ```bash
   pip install opencv-python numpy matplotlib
   ```

---

## 🚀 Step-by-Step Usage

### 1. Camera Calibration
Run `calibration.py` to calculate and save camera parameters:
```bash
python calibration.py
```
*Calculated parameters (`mtx.npy`, `dist.npy`, `rvecs.npy`, `tvecs.npy`, `ret.npy`) will be automatically saved in the `camera_params/` folder.*

### 2. Point Cloud Generation
Run `Projet.py` to process images and construct 3D point clouds using the saved calibration matrices:
```bash
python Projet.py
```
*Generated 3D output files will be saved in the `nuage_de_points/` directory.*

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
