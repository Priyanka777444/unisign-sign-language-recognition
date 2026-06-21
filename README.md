# Unisign: AI-Powered Sign Language Recognition

Real-time Gujarat Sign Language (GSL) recognition system that translates hand gestures into text/speech using computer vision and deep learning. Winner of a college-level competition and recipient of Smart India Hackathon (SIH) funding.

## Overview

Unisign uses MediaPipe for hand/pose keypoint extraction and a CNN + ConvLSTM2D-based deep learning model to classify sign language gestures from short video clips in real time.

## Architecture

1. **Video Input** — short video clips of individual signs, sampled at 10 evenly-spaced frames per clip
2. **Hand Region Extraction** — MediaPipe Hands detects hand landmarks per frame; the frame is cropped to the hand's bounding region
3. **Edge Feature Extraction** — Canny edge detection is applied to the cropped hand region, then resized to 128×128 grayscale, to emphasize gesture shape over background/lighting variation
4. **Temporal Modeling** — Conv3D + MaxPooling3D extract spatio-temporal features across the frame sequence, followed by an LSTM layer to model motion over time
5. **Classification** — Dense softmax layer outputs a prediction across the trained sign classes

## Tech Stack

Python, TensorFlow/Keras, OpenCV, MediaPipe, scikit-learn, NumPy

## Model Details

- **Layers:** Conv3D, MaxPooling3D, TimeDistributed(Flatten), LSTM, Dense
- **Validation/test accuracy:** 80%+
- **Training accuracy:** 95%

## Status

- Recognition model trained and validated in Google Colab (see `Model_02.ipynb`)
- Mobile app currently in **Early Access** (closed testing) on Google Play
  - Join the tester group: https://groups.google.com/g/unisign09/
  - Then access the app: https://play.google.com/store/apps/details?id=com.unisign.app

## Dataset

Custom-recorded video dataset of Gujarat Sign Language gestures, with multiple samples per sign to support training robustness.

## Acknowledgments

Developed as part of a Smart India Hackathon (SIH)-funded project and winner of a college-level competition.
