## From Source (Cache)

```sh
npm install --legacy-peer-dep
npm run build
```

Edit `package.json`:

```json
  "scripts": {
	...
    "start": "next start -p 7840",
    ...
  },
```

```sh
npm run start
```