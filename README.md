<h1 align="center">YOLOv8 Object Detection, Classification, and Tracking</h1>

## Install

```bash
# create python virtual environment
python3 -m venv venv

# install dependencies
pip install -r requirements.txt
```

## Execute

```bash
python3 -m main
```

## Algorithm 


Imports the necessary libraries - cv2 for video streaming and numpy for numerical computation. It also imports the YOLO class from the ultralytics library for object detection and the supervision library for annotating the detected objects and counting the number of objects that cross a specified line.

Defines two points LINE_START and LINE_END that represent the start and end points of a line that will be used to count the number of objects that cross it.

Defines three annotators - line_counter which counts the number of objects that cross the line, line_annotator which annotates the line on the video stream, and box_annotator which annotates the detected objects with boxes and labels.

Creates an instance of the YOLO model using the yolov8l.pt weights file.

Starts an infinite loop to process frames from the video stream. For each frame, the YOLO model is used to detect objects, and the resulting detections are converted to supervision format.

If the tracker_id is not None, the tracker_id is added to the detections.

Objects with class IDs of 60 and 0 are filtered out from the detections.

Labels are generated for each detected object, consisting of the tracker ID, class name, and confidence score.

The detected objects are annotated on the video stream using the box_annotator.

The line counter is triggered with the current detections, and the line is annotated on the video stream using the line_annotator.

The annotated video stream is displayed using the cv2.imshow function.

The loop continues until the user presses the ESC key, at which point the program exits.
