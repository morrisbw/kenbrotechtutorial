To set up virtual environment and install requirements
***myproject is probably best named myenv as to not be
so not to be confused with Django projects:

py -m venv myproject
.\myproject\Scripts\activate
pip install -r requirements.txt

.env contents:
DBNAME=restaurant
DBHOST=localhost
DBUSER=testuser
DBPASS=ThePassword@123

setttings.py within project DB configuration:
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': os.environ['DBNAME'],
        'HOST': os.environ['DBHOST'],
        'USER': os.environ['DBUSER'],
        'PASSWORD': os.environ['DBPASS'] 
    }
}

In VScode ctrl+shift+p to select proper interpreter