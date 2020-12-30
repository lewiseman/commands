## generate the requirements file
pip freeze > requirements.txt

## specify where to store django static files just above the static url
STATIC_ROOT = BASE_DIR / 'staticfiles'

## tell heroku how to serve them with whitenoise
add this in settings.MIDDLEWARE below security    
'whitenoise.middleware.WhiteNoiseMiddleware',

## add allowed hosts, name of app and local host url example
ALLOWED_HOSTS = ['text-test-heroku.herokuapp.com', '127.0.0.1:8000']

## create a runtime.txt file to put the python version required-
python-3.7.9

## create a Procfile file to say from where it would beserved
(make sure to have installed gunicorn in pip)  
web: gunicorn MovieReview.wsgi --log-file -   
MovieReview is folder where wsgi is located  
