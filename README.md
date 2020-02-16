# telegram-mtproto-javascript
This repository contains an improved version [**TelegramApi**](https://github.com/sunriselink/TelegramApi) that based on [**webogram**](https://github.com/zhukov/webogram).

List of improvements:
1. No more dependency on jQuery
2. Password verification implemented
3. Added support for HTTPS
4. Fixed the test mode


## Getting started

1) Install package via npm
```
npm install telegram-mtproto-javascript
```

2) Add a ```<script>``` to your index.html
```
<html>
<head>
    <title>My amazing app</title>
</head>
<body>
    <script src="node_modules/telegram-mtproto-javascript/dist/telegramApi.js"></script>
<body>
</html>
```

3) Set your app configuration
```
/* You should register your application on https://my.telegram.org/ */
telegramApi.setConfig({
  app: {
    id: 0, /* App ID */
    hash: 'qwertyasdfghzxcvbnqwertyasd', /* App hash */
    version: '0.0.0' /* App version */
  },
  server: {
    test: [
        { id: 1, host: '149.154.175.10', port: 80 },
        { id: 2, host: '149.154.167.40', port: 443 },
        { id: 3, host: '149.154.175.117', port: 80 },
    ],
    production: [
        { id: 1, host: '149.154.175.50', port: 80 },
        { id: 2, host: '149.154.167.50', port: 80 },
        { id: 3, host: '149.154.175.100', port: 80 },
        { id: 4, host: '1149.154.167.50', port: 80 },
        { id: 5, host: '149.154.171.5', port: 80 },
    ],
    https: [
        { id: 1, host: 'pluto.web.telegram.org', port: 80 },
        { id: 2, host: 'venus.web.telegram.org', port: 80 },
        { id: 3, host: 'aurora.web.telegram.org', port: 80 },
        { id: 4, host: 'vesta.web.telegram.org', port: 80 },
        { id: 5, host: 'flora.web.telegram.org', port: 80 },
    ]
  }
});
```

4) Check your status
```
telegramApi.getUserInfo().then(function(user) {
    if (user.id) {
        // You have already signed in
    } else {
        // Log in
    }
});
```

[API documentation](./docs/API.md)
