## Localhost

```sh
npm install
npm run build
```

```sh
npm run start
```

qBittorrent → Tools → Options → Web UI → Web USer Interface (On) → port `4321` → Authentication → Full in Username, Password

Open `localhost:4321`, login.

## Host on Ubuntu 22.04.4 ARM

Edit `package.json`:

```
{
	...
	"script": {
		"start": "node --enable-source-maps --use_strict dist/index.js",
	...
```

To:

```
{
	...
	"script": {
		"start": "node --enable-source-maps --use_strict dist/index.js --host 0.0.0.0 --port 4321",
	...
```

```sh
pm2 start npm --name "flood" -- run start
```

If you forget `username` or `password`, delete `flood` folder under `~/.local/shared/flood`. Reload or re-create flood's PM2-app.