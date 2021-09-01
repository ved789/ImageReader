# ImageReader
Recognizes an image based on pre-saved model
# To activate virtual env:
pip install virtualenv
virtualenv venv
venv\Scripts\activate
# To install all requirements:
pip install -r .\predictor_requirements.txt
# to start python type:
python
# install tensorflow:
pip install tensorflow
pip install tensorflow-gpu
# run the app
python .\predictor.py
# Open google cloud sdk shell and cd to D:\Hack\DEPLOY i e to this project direcotry
# And run these cmds to deploy to gcloud:
gcloud auth login
SET PROJECT_ID=lively-aloe-320309
set IMAGE_URI=asia.gcr.io/lively-aloe-320309/image_predictor
ECHO %IMAGE_URI%
gcloud builds submit --tag %IMAGE_URI%

gcloud run deploy --image %IMAGE_URI% --platform managed
