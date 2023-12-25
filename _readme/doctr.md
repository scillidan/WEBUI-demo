## Localhost

```sh
python3 -m venv venv
venv\Scripts\activate.bat
pip install "python-doctr[torch]"
pip install -r demo/pt-requirements.txt
```

```sh
set USE_TORCH=1
streamlit run demo/app.py
```

Or edit `demo/app.py`:

```py
import os
os.environ["USE_TORCH"] = "1"
...
```

```sh
streamlit run demo/app.py
```