# Emotion Detector

A Flask web application that analyzes a piece of text and detects the emotions in it. It uses the IBM Watson NLP emotion service and reports a score for each emotion, plus the dominant emotion.

Built as the final project of the IBM AI Developer course.

## Features

- Web page where you type a statement and get the emotion analysis
- Scores for five emotions: **anger, disgust, fear, joy, sadness**
- Shows the **dominant emotion** (the one with the highest score)
- Emotion detection logic packaged as a reusable Python module
- Unit tests for all five emotions

## Tech Stack

- **Python 3**
- **Flask** (web framework)
- **requests** (calls the Watson NLP API)
- **IBM Watson NLP** (emotion prediction)
- **unittest** (testing)
- **Git / GitHub** (version control)

## Project Structure

```
.
├── EmotionDetection/
│   ├── __init__.py
│   └── emotion_detection.py    # calls the Watson API and formats the result
├── static/                     # static files (JS/CSS)
├── templates/
│   └── index.html              # web page
├── server.py                   # Flask app and routes
├── test_emotion_detection.py   # unit tests
├── LICENSE
└── README.md
```

## How It Works

1. The user enters text on the web page.
2. The page sends the text to the `/emotionDetector` route in `server.py`.
3. `emotion_detector()` sends the text to the Watson NLP API and reads the JSON response.
4. The app returns the five emotion scores and the dominant emotion.

## Installation and Running

1. Clone the repository:

   ```bash
   git clone https://github.com/aqsa-05/oaqjp-final-project-emb-ai.git
   cd oaqjp-final-project-emb-ai
   ```

2. Install the dependencies:

   ```bash
   pip install flask requests
   ```

3. Start the app:

   ```bash
   python server.py
   ```

4. Open your browser at `http://localhost:5000`.

## Example

**Input:**

```
I am glad this happened
```

**Output:**

```
For the given statement, the system response is 'anger': 0.0064, 'disgust': 0.0025,
'fear': 0.0092, 'joy': 0.9682 and 'sadness': 0.0494. The dominant emotion is joy.
```

(Scores are example values and will vary slightly.)

You can also call the route directly:

```
http://localhost:5000/emotionDetector?textToAnalyze=I am glad this happened
```

## Running the Tests

```bash
python test_emotion_detection.py
```

The tests check that the dominant emotion is correctly detected for sample sentences expressing joy, anger, disgust, sadness and fear.

## What I Learned

- Building routes and rendering templates with Flask
- Calling a REST API with `requests` and parsing JSON responses
- Structuring code as a Python package
- Writing unit tests with `unittest`
- Using Git and GitHub to manage and publish a project

## License

This project is licensed under the terms of the LICENSE file included in this repository.
