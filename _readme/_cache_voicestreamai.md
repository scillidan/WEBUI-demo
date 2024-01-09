##

```sh
python39 -m venv venv
venv\Scripts\activate.bat
pip install transformers pyannote.core pyannote.audio websockets
```

Edit near line `28` of `serve.py`, add your token:

```py
VAD_AUTH_TOKEN = ""
```

```sh
python server.py
```