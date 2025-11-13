# face-Recognition-Attendance-System
This project is a Face Recognition Attendance System that uses a webcam to recognize faces in real-time and mark their attendance in a CSV file. It uses the face_recognition and OpenCV libraries to detect and identify faces based on pre-saved images stored in the Images folder.

When you run the program, your camera opens. It scans for any faces and checks if they match with the faces saved in the Images directory. If a match is found, the person’s name appears on the video feed, and their attendance is automatically recorded with the current time in an Attendance.csv file.

⚙️ Working Process
1. Loading Known Faces

The program first reads all the images from the folder named Images.

Each image filename represents the person’s name (e.g., John.jpg means the person’s name is “John”).

The images are converted into numerical encodings using the face_recognition library. These encodings represent the unique facial features of each person.

2. Encoding Faces

The function findEncodings() converts all images into face encodings.

These encodings are stored in a list called encodeListKnown.

This step allows the system to compare new faces detected by the camera with the known ones.

3. Starting the Webcam

The webcam is activated using cv2.VideoCapture(0).

Each video frame is captured and resized to one-fourth of its original size to make the face recognition process faster.

4. Detecting Faces in Real Time

The system detects all faces in the current webcam frame.

For each detected face, it generates a new face encoding and compares it with the known encodings from the Images folder.

5. Matching Faces

The program uses the compare_faces() and face_distance() functions to check how similar the live face is to the known ones.

The face with the smallest distance value is considered the closest match.

If a match is found, the system identifies the person’s name from the image filename.

6. Marking Attendance

Once a face is recognized, the function markAttendance(name) is called.

It opens the file Attendance.csv and checks if the person’s name is already marked.

If not, it records their name along with the current time using Python’s datetime module.

7. Displaying Results

A green rectangle is drawn around the recognized face.

The person’s name is displayed below the rectangle on the video feed.

The webcam window continues running, detecting and marking attendance in real-time.

You can stop the program anytime by closing the webcam window.

🧩 Libraries Used

OpenCV (cv2) — For webcam access, image processing, and drawing rectangles and text.

face_recognition — For detecting and comparing faces.

NumPy (np) — For numerical operations and face encoding comparisons.

datetime — To record the date and time of attendance.

os — For reading files from the image directory.
