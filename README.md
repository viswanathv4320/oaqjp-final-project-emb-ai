# Final Project: NLP Emotion Detection Application

## Overview
A web-based Emotion Detection application built using IBM Watson NLP embeddable AI libraries, packaged as a Python module, tested with unit tests, and deployed using Flask.

## Project Structure
```
oaqjp-final-project-emb-ai/
├── EmotionDetection/
│   ├── __init__.py
│   └── emotion_detection.py
├── static/
│   └── mywebscript.js
├── templates/
│   └── index.html
├── server.py
└── test_emotion_detection.py
```

## Tasks Completed

### Task 1: Fork and Clone the Repository
- Forked the IBM Developer Skills Network repository to personal GitHub account
- Cloned the forked repository into the IBM Skills Network Cloud IDE
- Updated README.md with project name: **Final project**

### Task 2: Create the Emotion Detection Application
- Created `emotion_detection.py` with the `emotion_detector` function
- Used IBM Watson NLP **Emotion Predict** API via HTTP POST requests
- Function accepts text input and returns the raw API response

### Task 3: Format the Output
- Parsed the Watson NLP JSON response using the `json` library
- Extracted five emotion scores: `anger`, `disgust`, `fear`, `joy`, `sadness`
- Identified the dominant emotion using `max()` with `key=dict.get`
- Returns a structured dictionary with all scores and dominant emotion

### Task 4: Package the Application
- Created the `EmotionDetection` Python package folder
- Added `__init__.py` to expose `emotion_detector` as a public function
- Validated the package by importing and testing it in a Python shell

### Task 5: Run Unit Tests
- Created `test_emotion_detection.py` using Python's `unittest` framework
- Wrote 5 test cases validating the dominant emotion for each statement:

| Statement | Expected Dominant Emotion |
|---|---|
| I am glad this happened | joy |
| I am really mad about this | anger |
| I feel disgusted just hearing about this | disgust |
| I am so sad about this | sadness |
| I am really afraid that this will happen | fear |

- All 5 unit tests passed successfully

### Task 6: Web Deployment Using Flask
- Created `server.py` to deploy the application on `localhost:5000`
- Defined two Flask routes:
  - `GET /` — renders the main HTML interface
  - `GET /emotionDetector` — runs emotion detection and returns formatted response

### Task 7: Error Handling
- Updated `emotion_detector` to handle `status_code = 400` (blank input)
- Returns dictionary with all values set to `None`
- Server returns: `"Invalid text! Please try again!"`

### Task 8: Static Code Analysis
- Ran `pylint` on `server.py`
- Achieved a perfect **10/10 pylint score**

## Technologies Used
- Python 3.11
- Flask
- IBM Watson NLP (Emotion Predict API)
- `requests` and `json` libraries
- `unittest` framework
- `pylint` for static code analysis
- Git for version control

## How to Run
```bash
git clone https://github.com/viswanathv4320/oaqjp-final-project-emb-ai.git
cd oaqjp-final-project-emb-ai
pip install flask requests
python3 server.py
```

## Running Unit Tests
```bash
python3 test_emotion_detection.py
```
