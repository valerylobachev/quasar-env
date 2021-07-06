# How to use environment variables in Quasar app

## Setup environment variables

1. Add environment variables you want to use (in our case we use environment variable `MY_API` with alias `API_SERVER`)
   in `quasar.conf.js` in `build` section:

```js
    env: {
            API_SERVER: process.env.MY_API
        }
```

2. Create code(`api.service.ts`) that use value of environment variable (in our case we access it using alias `API_SERVER`):

```js
export const API_SERVER = process.env.API_SERVER || 'https://dev.server.com/api';
```

3. Run application in dev mode to use default value `https://dev.server.com/api`:

```bash
quasar dev
```

4. Run application in dev mode with defined environment variable `MY_API` :

```bash
export MY_API="https://qa.server.com/api"
quasar dev
```

## Build application using environment variable

1. Add build scripts to `package.json`:

```json
{
  "scripts": {
    "build-dev": "export MY_API=\"https://dev.server.com/api\" && quasar build",
    "build-qa": "export MY_API=\"https://qa.server.com/api\" && quasar build",
    "build-prod": "export MY_API=\"https://prod.server.com/api\" && quasar build"
  }
}
```

2. Build application with environment you need:

```bash
yarn build-prod
```
