# Covid-19-Face-Mask-and-Social-Distancing-Detection

This project is used to detect face mask and social distancing violations from input image, video and webcam feeds.

## Models and Techniques
Pretrained **Yolov3** is used to detect people

Pretrained **SSD** is used to detect faces

Trained **MobileNetV2** is used as face mask classifier

**Euclidean distance** is used to calculate social distancing violations

## Getting Started
### Prerequisites
* face-detection
* flask
* imutils
* keras
* matplotlib
* opencv-python
* pandas
* scikit-learn
* tensorflow
* opencv-python

## Quickstart (Demo)
Download the pretrained Yolov3 weights using this [link](https://drive.google.com/file/d/1gqdAighUzlkg-ogA8PWRuPfOH0y8OpMI/view?usp=sharing) and save it to the `yolo-coco/` directory

Create a virtual environment and install the required dependencies using the command `pip install -r requirements.txt`

#### Face mask detection on images
Test the face mask classifier using the command `python detect_face_mask_image.py --image input/image/path`

The output image is stored as `output_fm.png`

You can also use the flask web app using the command `python app.py` and the application runs in the address http://0.0.0.0:12000/

#### Social distancing detection on images
Test the social distancing detection on images using the command `python detect_social_distance_image.py --image input/image/path --distance [default=100.0]`

Experiment `--distance` value for different images. The output is stored as `output_sd.jpg`

### Face mask and social distancing detection on videos/webcam
Use the command `python video.py --video input/video/path --distance [default=100.0] --frames [default=20]` to test on video files

Experiment `--distance` value for different video files and `--frames` to skip frames. The result frames are stored in `result_frames/` directory

Use the command `python webcam.py` to test using a webcam device

### Docker for Face Mask Detection on Images
Use the Docker image to run the face mask detector microservice 

Pull the docker image using the command **docker pull rakeshraj97/project1:0.0.1**

Run the docker using the command **docker run -p 12000:12000 rakeshraj97/project1:0.0.1**

Ensure working of the microservice using the command **curl http://0.0.0.0:12000/** or open the link **http://0.0.0.0:12000/** in a web browser to use the web application


## Train Face Mask Detector
