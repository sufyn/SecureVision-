# Smoking Detection System

This project implements a Flask web application for real-time smoking detection using both image and video inputs. It uses a custom-trained Haar Cascade model and a YOLO-based deep learning model for smoking detection. The system provides both static image processing and live video streaming for detecting smoking instances.

## Features
- **Static Image Smoking Detection**: Upload an image and the system detects smoking areas in the image using the Haar Cascade classifier.
- **Real-time Video Smoking Detection (Haar Cascade)**: Stream video from the webcam and detect smoking in real-time.
- **Real-time Video Smoking Detection (YOLO)**: Another option for live video detection, using a YOLO deep learning model to identify smoking instances.
- **Web Interface**: User-friendly web pages for interacting with the application.
- **Live Streaming**: Continuous video streaming for real-time detection of smoking instances.

## Installation

### Requirements

- Python 3.x
- Flask
- OpenCV
- NumPy

### Setup

1. Clone this repository:
   ```bash
   git clone <repository_url>
   cd <repository_folder>
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download the Haar Cascade model for smoking detection (`naya.xml`) and the YOLO model (`strong.onnx`) and place them in the `./static` directory.

4. Run the application:
   ```bash
   python app.py
   ```

The web application will be accessible at `http://127.0.0.1:5000/`.

## Endpoints

- **`/`**: Home page with the main interface.
- **`/after`**: Endpoint for processing an uploaded image and detecting smoking using Haar Cascade.
- **`/har_vd`**: Real-time webcam video stream with smoking detection using Haar Cascade.
- **`/vd_feed`**: Video feed for real-time smoking detection from the webcam.
- **`/yolo_after`**: Endpoint for processing an uploaded image using the YOLO model for smoking detection.
- **`/yolo_vd`**: Real-time webcam video stream with smoking detection using YOLO.
- **`/yvd_feed`**: Video feed for real-time smoking detection using YOLO from the webcam.
- **`/open_webcam`**: Start the webcam stream for detecting smoking using YOLO.

## Template Pages

- **`index.html`**: The main page for interaction.
- **`har-web.html`**: Interface for Haar Cascade-based detection.
- **`yolo-web.html`**: Interface for YOLO-based detection.
- **`Mujahid.html`**, **`Kaif.html`**, **`Faiz.html`**, **`Anas.html`**: Different pages for team members.

## How it Works

### Image Processing:
- Users can upload images to the `/after` endpoint, and the system will process the image, detect faces, and check for smoking using a Haar Cascade classifier.
  
### Video Processing:
- The system continuously streams the webcam feed using OpenCV. The `/har_vd` and `/yolo_vd` routes handle real-time smoking detection with Haar Cascade and YOLO respectively.

### YOLO Model:
- The YOLO model (`strong.onnx`) is used to detect smoking with better accuracy. The input images are formatted to fit the model’s input dimensions (640x640) and predictions are displayed in real-time.

## Example Usage

1. **Upload an Image**: 
   - Visit `/after` and upload an image. The system will process it and show the result on the next page.
  
2. **Start Video Stream**:
   - Visit `/har_vd` or `/yolo_vd` to start a video stream. The system will use the webcam feed to detect smoking in real-time.
  
3. **YOLO vs Haar Cascade**:
   - You can choose between using the Haar Cascade (`/har_vd`) or YOLO (`/yolo_vd`) for video streaming. YOLO typically provides better accuracy.

## Contributions

Feel free to fork this project and contribute! Please create a pull request if you wish to contribute to this project.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
