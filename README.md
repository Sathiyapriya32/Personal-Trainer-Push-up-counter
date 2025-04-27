# Personal Trainer Push-up Counter

This project uses **MediaPipe** and **OpenCV** to count push-ups in real-time by detecting and tracking the user's pose. The program calculates the angle between the shoulder, elbow, and wrist during a push-up to determine when a push-up is completed.

## Prerequisites

Ensure you have the following installed:

- Python 3.x
- `opencv-python`
- `mediapipe`
- `numpy`

You can install the required dependencies using the following command:

```bash
pip install opencv-python mediapipe numpy
```
## Code Overview
1. Imports:
We import OpenCV, MediaPipe, and NumPy to capture video, detect pose landmarks, and perform angle calculations.

2. Pose Detection Setup:
We initialize the MediaPipe Pose solution with a minimum detection confidence and minimum tracking confidence.

3. Angle Calculation Function:
The function calculate_angle(a, b, c) calculates the angle between three points (shoulder, elbow, and wrist) using the arctangent of the differences in their x and y coordinates. The angle is used to determine the push-up stage.

4. Push-up Counter Logic:
We track the angle between the shoulder, elbow, and wrist to count the number of push-ups:

When the angle is greater than 160°, the stage is "up."

When the angle is less than 90° and the stage is "up," the stage changes to "down," and the counter increases by 1.

5. Rendering:
The angle is displayed on the screen near the elbow.

The current push-up count is displayed at the top left of the screen.

Pose landmarks and connections are drawn to visualize the user's pose.

6. Exit:
Press the 'q' key to stop the webcam feed and exit the application.
