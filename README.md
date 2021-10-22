# ignite-team6
Sign Language recognition using TensorFlow and Mediapipe. 

## model-training
To run the code in the folder, install the following dependencies
```
!pip install tensorflow==2.4.1 tensorflow-gpu==2.4.1 opencv-python mediapipe sklearn matplotlib pyttsx3
```

### Action Detection Notebook 
Notebook with code to collect data and train LSTM model. Notebook is commented on and has the following sections, 
1. Setup Dependencies, Libraries, Helper Functions
2. Setup Folders for Data Collection
3. Collect keypoints for training
4. Training Model
5. Test Detection, Demo
6. MediaPipe Holistc Demo
7. Convert model to tflite

Although simple, the 3 layer LSTM model offers the following benefits
- Less data is required for training, as relevant dataset does not exist.
- Faster training, model has 203,624 trainable parameters.
- Faster detections in real time, lightweight model allows for faster prediction, especially for edge devices with low computing resources.

### sample data/google
Shows exported numpy arrays of keypoints used as data to train the LSTM model, entire dataset is not uploaded because there are thousands of small files which limits upload speed (eg. 10 words x 50 videos for each word x 30 frames for each word represented by exported npy array)


### model_tester.py
Code to test the model on a live webcam feed using OpenCV. Outputs predicted text on video feed and has text-to-speech implemented (video feed out might lag for text to speech as threading has not been implemented).

Model used for this demo is able to recognize the following words: _please, hire, me, google_.

<img src="https://github.com/wushennn/ignite-team6/blob/main/action_hireme.gif" width="370" height="200">

When testing model:

1. Adjust threshold accordingly (determines probability in which predicition is accepted).
2. As dataset is small, position matters. User should position themselves in the centre of the video feed and be about one arms length away from the computer.
3. Ensure that hand is being detected.


## rpi-local-deployment

### cvs_capture.py
This code is used for testing the RPI that also shows the output live on the RPI via the user interface.

### MainRunner.py
This code starts up the entire processing with the video capture being done on one thread while the inference runs on another thread.

### VideoCapture.py
This class is used to run the video capture in a thread of its own.

### InferenceEngine.py
This class can be used to run the inference in another thread. It is not used in the deployment currently.

## model
Archive intermediate code and models, 
- Sentence 1: let us discuss our agenda
- Sentence 2: im doing well thanks
- Sentence 3: Sentence 1 + 2
