# Unisign: AI-Powered Sign Language Recognition

Real-time Gujarat Sign Language (GSL) recognition system that translates hand gestures into text/speech using computer vision and deep learning. Winner of a college-level competition and recipient of Smart India Hackathon (SIH) funding.

## Overview

Unisign uses MediaPipe for hand/pose keypoint extraction and a CNN + ConvLSTM2D-based deep learning model to classify sign language gestures from short video clips in real time.

## Architecture

1. **Video Input** — short video clips (1-2 sec) of individual signs, recorded as training data
2. **Keypoint Extraction** — MediaPipe extracts hand and pose landmarks frame-by-frame, reducing raw video to structured keypoint sequences
3. **Temporal Modeling** — ConvLSTM2D layers process the sequence of keypoints over time to capture motion patterns specific to each sign
4. **Classification** — Dense layers output a prediction across the trained sign classes

## Tech Stack

Python, TensorFlow/Keras, OpenCV, MediaPipe, scikit-learn, NumPy

## Model Details

- **Layers:** ConvLSTM2D, MaxPooling3D, TimeDistributed, LSTM, Dense
- **Training accuracy:** 95%
- *Note: this is training accuracy. Validation/test-set accuracy on unseen signers has not yet been formally measured — a planned next step is to evaluate on a held-out validation split to confirm real-world generalization.*

## Status

- Recognition model trained and validated in Google Colab (see `Model_02.ipynb`)
- Mobile app in development — [link to be added once public]

## Dataset

Custom-recorded video dataset of Gujarat Sign Language gestures, with multiple samples per sign to support training robustness.

## Acknowledgments

Developed as part of a Smart India Hackathon (SIH)-funded project and winner of a college-level competition.
