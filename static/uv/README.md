# uv-scripts
Core Uv scripts

# Configuration
Configure uv for both client-hooking & service worker in `uv.config.js`
```javascript
self.__uv$config = {
    bare: '/bare/',
    prefix: '/service/',
    encodeUrl: uv.codec.xor.encode,
    decodeUrl: uv.codec.xor.decode,
    handler: '/uv.handler.js',
    bundle: '/uv.bundle.js',
    config: '/uv.config.js',
};
```


# Example Usage
```javascript
importScripts('/PATHTOSCRIPTS/uv.sw.js');

const sw = new UVServiceWorker();

self.addEventListener('fetch', event =>
    event.respondWith(
        sw.fetch(event)
    )
);
```
