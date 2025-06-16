# Voice-Recogition
# 🎙️ Attendance System Through Voice Recognition

An automated biometric attendance system that uses **voice recognition** to identify and mark student attendance. Built using **Python**, **PyQt5**, and **Gaussian Mixture Models (GMM)**, this project presents a contactless, secure, and efficient alternative to manual attendance marking in classrooms.

## 📌 Features

- 🎤 **Voice-based identification** using trained speaker models
- 🧠 **Gaussian Mixture Model (GMM)** for voice pattern classification
- 🛠️ **MFCC feature extraction** and delta calculations
- 🧪 Functions for **training**, **testing**, and **real-time attendance marking**
- 🖥️ Clean and simple **GUI interface** using PyQt5
- 📈 Accuracy analysis and performance evaluation

## 🧰 Tech Stack

- Python 3
- PyQt5
- NumPy
- Scikit-learn
- Pyaudio
- SpeechRecognition
- SciPy

## 🚀 Getting Started

### Prerequisites

Install the required packages:

```bash
pip install numpy scipy PyQt5 scikit-learn pyaudio SpeechRecognition
```
## 🛠️ How It Works
### Training Phase:

- Run TrainData.ipynb.
- Select the option to record voice samples for each student.
- You can control the RECORD_SECONDS in the function record_audio_train().
- You can control the number of samples recorded per user by changing the number of iterations in record_audio_train() loop.
- MFCC features are extracted and saved.
- Run TrainData.ipynb if need be and now select the option 'Train Model' to train the model.
- GMMs are trained and stored per speaker.

### Testing/Attendance Phase:
- Run TestData.ipynb
- Enter the name same as you did while training
- GUI allows the student to record a short voice sample..
- The system compares the sample to all trained models.
- If a match is found, the student's attendance is marked.

### Folders and .txt Files:
- These files are important and are used in the code for maintaining voice recordings.
- training_set_addition.txt contains the .wav file names of all the recorded samples and these names are read from this file when training the model.
- testing_set_addition.txt contains the .wav file name of the voice being tested at run time.
- training_set folder contains all the .wav files taken from the user to train the model. The files are automatically saved in this location as long as the folder is in the same directory as TrainData.ipynb.
- trained_models folder contains all the .gmm models trained from the .wav files in the training_set. The files are automatically accessed from training_set folder and the .gmm saved in the trained_models folder as long as the folder is in the same directory as TrainData.ipynb.
- testing_set contains the .wav file of the voice being tested at run time.

### GUI:

Developed in PyQt5.

Button-driven interface: Mark Attendance triggers real-time recording and recognition.

Displays messages for recognition success or failure.

### 🔍 Observation:

Accuracy improves with distinct voice features and larger sample sizes.

## ⚠️ Limitations
Fails to reject unknown voices (i.e., always matches to closest trained speaker).

Sensitive to background noise and microphone quality.

Sample size greatly influences recognition accuracy.

Lack of real-time feedback timer (scrapped due to GUI conflicts).

## 📈 Future Improvements
Implement rejection for unknown voices.

Add real-time countdown timer for voice recording.

Expand to cloud-based voice authentication services.

Store attendance logs in CSV format per course.


