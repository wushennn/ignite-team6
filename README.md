# ignite-team6
Sign Language recognition using to TensorFlow and Mediapipe. 

- upload tflite, h5 please hire me model
- upload clean notebook
- upload rpi code
- upload gif
- dataset not included because too many small files (very troublesome to upload)



Although simple, our model has the following benefits:

Less data is required for training, as relevant dataset does not exist.
Faster training, model has 203,624 trainable parameters.
Faster detections in real time, lightweight model allows for faster prediction, especially for edge devices with low computing resources.

## model_tester.py
Code to test the model on a live camera feed (current device) using OpenCV. Outputs predicted text on video feed and has text-to-speech implemented.

When testing model:

Adjust threshold accordingly (determines probability in which predicition is accepted).
As dataset is small, position matters. User should position themselves in the centre of the video feed and be about one arms length away from the computer.
Ensure that hand is being detected.
