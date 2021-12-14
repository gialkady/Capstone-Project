
## Local Deployment

Tools: mac laptop, pycharm and anaconda3

After the final model is obtained, apply the next steps:
- Convert notebook into .py file -> train.py
- Put all required files (ex. model_trained_101class.tflite)
- Make a virtual enviroment for deep learning includig (python 3.7.11, tensorflow, tflite 2.4.0, tflite-runtime 2.5.0, keras-image helper)
- Open terminal in project folder and test file without docker -> python3 train.py
- Download docker in terminal or if you mac user download "docker for mac".
- Build docker image (write all dependencies needed to run model) -> 'Docker build -t food_classification .'
- Run model in the docker container in terminal 
- Test response file
