# Real-Time Object Tracking & Directional Line Counter

A production-ready computer vision pipeline designed for automated traffic flow analysis, vehicle counting, and directional transit monitoring using deep learning detectors and multi-object tracking algorithms.

## 📌 Problem & Solution Overview
Frame-by-frame object detection cannot inherently maintain identity across temporal sequences, resulting in duplicate counts for persistent objects. 

This project implements a complete tracking-by-detection architecture:
1. **Detection:** Extracts spatial coordinates and class bounding boxes using YOLOv8.
2. **Temporal Association:** Integrates ByteTrack to assign invariant tracking IDs across sequential frames.
3. **Boundary Crossing Logic:** Utilizes custom Euclidean centroid-tracking logic to detect bidirectional line crossings while filtering duplicates via ID caching.

## 🛠 Tech Stack
- **Inference Engine:** YOLOv8 (Ultralytics)
- **Multi-Object Tracking:** ByteTrack
- **Frame Processing & Geometry:** OpenCV, NumPy
- **Dataset / Target Classes:** COCO (Cars, Buses, Trucks, Motorcycles)

## 📊 Performance & Results
- **Track Association Stability:** Successfully maintains identity across temporal occlusions.
- **Deduplication:** State memory ensures zero double-counting per unique transit vector.

## 🚀 Getting Started

```bash
# Clone the repository
git clone [https://github.com/EnverKangal/realtime-object-tracking-and-line-counting.git](https://github.com/EnverKangal/realtime-object-tracking-and-line-counting.git)

# Install requirements
pip install ultralytics supervision opencv-python numpy

# Execute tracking script
python tracker_counter.py
