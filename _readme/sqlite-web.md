## Localhost

Use `pipx`:

```sh
pipx install sqlite-web
```

```sh
sqlite_web yourdatabase.db
```

Or use `-m venv`

```sh
python39 -m venv venv
venv/Scripts/activate.bat
pip install .
```

```sh
venv/Scripts/sqlite_web.exe yourdatabase.db
```