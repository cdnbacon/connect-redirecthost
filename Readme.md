# Connect Host Redirect

connect-redirecthost is middleware for the Express.js framework that allows redirecting multiple domains to a default one.

## Installation

    $ npm install node-force-domain

## Quick Start

Using connect-redirecthost is easy. Register it within Express.js as middleware by adding the following line into your app.js file before most calls to app.use(...):

```javascript
app.use(require('connect-redirecthost').redirectHost('www.example.com'));
```

Localhost is always excluded to make local development easier.

### Exceptions

Redirect exceptions are supported. If, for example, your site uses a CDN on a separate domain, you can create an exception for that domain

```javascript
app.use(require('connect-redirecthost').redirectHost({
 to: 'www.example.com',       // all requests not on www.example.com will be redirected to www.example.com
 except: 'cdn.example.com'    // except for those to cdn.example.com
}));
```

You can also specify multiple exceptions using an array.

```javascript
app.use(require('connect-redirecthost').redirectHost({
 to: 'www.example.com',
 except: ['cdn.example.com', 'origin.example.com']
}));
```


## License

View the LICENSE file.

