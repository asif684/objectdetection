## YOLOv8 Object Detection and Tracking with OpenCV

This project demonstrates real-time object detection using a YOLOv8 model and object tracking using OpenCV. The code captures live video from a webcam, detects objects using a pretrained YOLOv8 model, and tracks a selected object.

---

## Requirements

To run this project, ensure you have the following installed:

1. **Python 3.8+**
2. **Libraries:**
   - `ultralytics`
   - `opencv-python`
   - `opencv-contrib-python`
   - `torch`
   - `numpy`

Install the required libraries using pip:

```bash
pip install ultralytics opencv-python opencv-contrib-python torch numpy
```

---

## Project Setup

1. **Clone the Repository or Download the Script**
   - Save the code in a Python file, e.g., `object_tracking.py`.

2. **Prepare the YOLOv8 Model**
   - Train or obtain a pretrained YOLOv8 model.
   - Save the model file (e.g., `best.pt`) in an accessible directory.
   - Update the model path in the code:
     ```python
     model = YOLO(r"C:\path\to\your\model\best.pt")
     ```

3. **Ensure Webcam Access**
   - Ensure your device has a working webcam.

---

## How It Works

1. **Object Detection**:  
   The YOLOv8 model detects objects in the webcam feed. Bounding boxes are created for objects with confidence scores above the threshold.

2. **Object Tracking**:  
   Once a bounding box is selected, the OpenCV `TrackerCSRT` is initialized to track the object across subsequent frames.

3. **Output Display**:  
   The webcam feed is displayed with:
   - Bounding boxes for detected or tracked objects.
   - A label showing the coordinates of the tracked object.

4. **User Controls**:  
   - Press **`q`** to exit the application.

---

## Key Features

- **Real-time Object Detection**: Uses YOLOv8 for fast and accurate detection.
- **Object Tracking**: Tracks a single object using OpenCV's `TrackerCSRT`.
- **Adjustable Confidence Threshold**: Customize detection sensitivity.

---

## How to Run

1. Open a terminal and navigate to the directory containing the script.
2. Run the script using:
   ```bash
   python object_tracking.py
   ```
3. The webcam feed will open, and object detection and tracking will begin.

---

## Notes

- **Confidence Threshold**:  
  Adjust the `CONFIDENCE_THRESHOLD` variable in the script to control detection sensitivity:
  ```python
  CONFIDENCE_THRESHOLD = 0.5
  ```

- **Tracker Selection**:  
  Replace `cv2.TrackerCSRT_create()` with other tracker types if needed:
  - `cv2.TrackerKCF_create()`
  - `cv2.TrackerMIL_create()`
  - `cv2.TrackerMOSSE_create()`

---

## Example Output

- Objects detected and tracked will have bounding boxes drawn in green.
- Coordinates and dimensions of tracked objects will appear as text labels.

---

## Troubleshooting

- **Webcam Error**: Ensure your webcam is properly connected and accessible.
- **Model Path Error**: Verify the path to your YOLOv8 model file.
- **Tracking Fails**: If tracking fails, the tracker will reset, and detection will resume.

---

## License

This project is open-source and available for modification and use for personal or educational purposes. Attribution is appreciated.

---
