## Localhost

```sh
python39 -m venv venv
venv\Scripts\activate.bat
pip install calibreweb[metadata]
```

```sh
cps
```

Open `localhost:8083`. If your want to shotdown the process, `Ctrl+C` and refresh the web-page.

Login with default Username `admin` and Password `admin123`. If you want to edit account: admin → Edit `Username`, `Email`, `Password` → Save

Open Calibre → Add books ...

Calibre-Web → Admin → Edit Cabibre Database Configuration → Select folder contains `metadata.db`, liked `calibre\Calibre Library`.

## Use OPDS

[Thorium](https://github.com/edrlab/thorium-reader) → Catalogs → Add an OPDS feed → Name `calibre-web`, Link `http://localhost:8083/opds`

## Sever with Calibre

1. Calibre → Preferences → Sharing/Sharing over ht net → The port on which to listen for connections `8084`
2. Calibre → Connect/share → Start Content server
3. Thorium → Catalogs → Add an OPDS feed → Name `calibre`, Link `http://localhost:8084/opds`

But can't add books with `calibredb add ... --with-library ...\data_calibre` when `calibre-server.exe --port 8084 ...\data_calibre` running.