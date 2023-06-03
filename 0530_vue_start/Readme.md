# Vue 공식 문서 예제

## 명령어

```sh
npm init -y
node example.js
# package.json > "type":"module"
npm install vue
example.js # create
```

```javascript
import { createSSRApp } from 'vue';
// Vue's server-rendering API is exposed under `vue/server-renderer`.
import { renderToString } from 'vue/server-renderer';

const app = createSSRApp({
    data: () => ({ count: 1 }),
    template: `<button @click="count++">{{ count }}</button>`,
});

renderToString(app).then((html) => {
    console.log(html);
});
```

```sh
node example.js
npm install express
```

```javascript
// server.js
import express from 'express';
import { createSSRApp } from 'vue';
import { renderToString } from 'vue/server-renderer';

const server = express();

server.get('/', (req, res) => {
    const app = createSSRApp({
        data: () => ({ count: 1 }),
        template: `<button @click="count++">{{ count }}</button>`,
    });

    renderToString(app).then((html) => {
        res.send(`
    <!DOCTYPE html>
    <html>
      <head>
        <title>Vue SSR Example</title>
      </head>
      <body>
        <div id="app">${html}</div>
      </body>
    </html>
    `);
    });
});

server.listen(3000, () => {
    console.log('ready');
});
```
