# YOLO11n Object Detection Model

## Overview

`yolo11n.pt` is an ultra-lightweight object detection model based on the YOLO architecture. It is optimized for devices with limited computational resources, offering a balance between speed and accuracy. This model is ideal for real-time applications such as video surveillance, mobile apps, and IoT devices.

## Key Features

- **Compact Size**: The model file is approximately 1 MB, suitable for resource-constrained environments.
- **Real-Time Performance**: High frame rates on CPUs and mobile GPUs.
- **Versatile Applications**: Supports a wide range of object detection tasks.

## Performance

| Metric          | Value           |
|-----------------|-----------------|
| **mAP@0.5**     | 35.2%          |
| **FPS (CPU)**   | ~35 FPS        |
| **FPS (GPU)**   | ~120 FPS       |

Tested on the COCO dataset (2017) and a custom dataset for object detection tasks.

## Getting Started

### 1. Installation

Install the YOLO library to use the `yolo11n.pt` model:

```bash
pip install ultralytics
```

### 2. Usage

#### Running Object Detection

```python
from ultralytics import YOLO

# Load the model
model = YOLO("yolo11n.pt")

# Run detection on an image
results = model("input.jpg")

# Display results
results.show()
```

#### Customizing Parameters

- **Confidence Threshold**: Set a confidence threshold to filter out low-confidence detections:

  ```python
  results = model("input.jpg", conf=0.25)
  ```

- **IoU Threshold**: Adjust the IoU threshold for overlapping detections:

  ```python
  results = model("input.jpg", iou=0.5)
  ```

### 3. Visualization

To save detection results with annotations:

```python
results.save("output_folder/")
```

### 4. Batch Processing

Run detection on a directory of images:

```python
results = model("input_folder/*.jpg")
```

## Applications

- **IoT Devices**: Real-time object detection on edge devices.
- **Surveillance**: Monitoring with live video feeds.
- **Mobile Apps**: Lightweight models for on-device processing.

## Advantages

- Compact and fast.
- Easy to integrate.
- Suitable for real-time applications.

## Limitations

- Lower accuracy on complex scenes with many small objects.
- Limited performance compared to larger YOLO models.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Ultralytics YOLO](https://github.com/ultralytics/ultralytics) for providing the YOLO framework.
- Community contributors for dataset and testing support.
