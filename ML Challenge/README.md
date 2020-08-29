<b>ML Coding Challenge</b>

```
git clone https://github.com/abbas5253/emotion-detector-youbotics.git
```

## Face-Emotion-Detector

### Prerequisites
You mast have pytorch and opencv-python installed

## Emotion Detector

### Project Structure
This project has four major parts :
1. model.py - This contains code fot our Machine Learning model to predict based on the weights/weights.pth.
2. app.py - This contains Flask APIs that receives frame API calls, this predict and returns the experession.
3. frontend.py - This uses requests module to call APIs already defined in app.py and dispalys the returned value.
4. preprocess.py - This is used for preprocessing the input frame

### Running the project
1. Ensure that you are in the project home directory. Create the machine learning model by running below command.
```
python model.py
```
This would create a serialized version of our model into a file model.pkl

2. Run app.py using below command to start Flask API
```
python app.py
```
By default, flask will run on port 5000.

3. Navigate to URL http://localhost:5000/predict

4. This will open your web cam to evaluate expression

