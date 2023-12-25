## Localhost

```sh
python3 -m venv env
env\Scripts\activate.bat
pip install django reportbro-lib
python manage.py makemigrations albums
python manage.py migrate
python manage.py compilemessages
```

```sh
env\Scripts\python manage.py runserver localhost:8010
```

Open `localhost:8010/albums`