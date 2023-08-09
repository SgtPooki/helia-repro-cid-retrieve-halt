## 0. Setup

Clone this repo:

```sh
$ git clone https://gist.github.com/5565c22255ae87a3c8e9948b467ee894.git helia-b2l-buggy
$ cd helia-b2l-buggy/
```

Generate `npm-browser.js` npm package bundle:

```sh
$ npm i
$ npm run build
```

## 1. Run successful case

```sh
$ node case-success.mjs

[middle info URL] http://localhost:54399/
[peerId on nodejs] 12D3KooWD7QJaTzmJyehjzctLNywWrWnpurue6bAnxvALcKw3PTr
[page server url] http://localhost:54405/index.html
(node:78124) [DEP0066] DeprecationWarning: OutgoingMessage.prototype._headers is deprecated
(Use `node --trace-deprecation ...` to show where the warning was created)
{ url: '', lineNumber: 4, columnNumber: 10 } [peerId on browser] 12D3KooWDHrcijYVQgpDZAgP3cakDXfVrsghS9SXnDxtJhd2n1f5
[stat of cid from browser] {
  cid: CID(bafkreif5viehisdkgsxmfrmu5crzazgqhtg7xaifnjzyrcypsddkfnecaa),
  mode: undefined,
  mtime: undefined,
  fileSize: 18n,
  dagSize: 18n,
  localFileSize: 18n,
  localDagSize: 18n,
  blocks: 1,
  type: 'raw',
  unixfs: undefined
}
[text of cid from browser] Hello from browser
{ url: '', lineNumber: 4, columnNumber: 12 } [peer.id] 12D3KooWD7QJaTzmJyehjzctLNywWrWnpurue6bAnxvALcKw3PTr
{ url: '', lineNumber: 5, columnNumber: 12 } [peer.multiaddrs.length] 6
{ url: '', lineNumber: 6, columnNumber: 46 } [peer.multiaddrs] /ip4/127.0.0.1/tcp/54397/p2p/12D3KooWRNKNQ28o7akKCMfXRRSgYKyFan3qxm7S83ULmVzFu8Lm/p2p-circuit
{ url: '', lineNumber: 6, columnNumber: 46 } [peer.multiaddrs] /ip4/127.0.0.1/tcp/54398/ws/p2p/12D3KooWRNKNQ28o7akKCMfXRRSgYKyFan3qxm7S83ULmVzFu8Lm/p2p-circuit
{ url: '', lineNumber: 6, columnNumber: 46 } [peer.multiaddrs] /ip4/127.0.0.1/tcp/54402
{ url: '', lineNumber: 6, columnNumber: 46 } [peer.multiaddrs] /ip4/192.168.10.6/tcp/54397/p2p/12D3KooWRNKNQ28o7akKCMfXRRSgYKyFan3qxm7S83ULmVzFu8Lm/p2p-circuit
{ url: '', lineNumber: 6, columnNumber: 46 } [peer.multiaddrs] /ip4/192.168.10.6/tcp/54398/ws/p2p/12D3KooWRNKNQ28o7akKCMfXRRSgYKyFan3qxm7S83ULmVzFu8Lm/p2p-circuit
{ url: '', lineNumber: 6, columnNumber: 46 } [peer.multiaddrs] /ip4/192.168.10.6/tcp/54402
{ url: '', lineNumber: 7, columnNumber: 12 } [peer.protocolss.length] 0
{ url: '', lineNumber: 13, columnNumber: 10 } [stat of cid from nodejs] {cid: _CID, mode: undefined, mtime: undefined, fileSize: 17n, dagSize: 17n}
{ url: '', lineNumber: 19, columnNumber: 10 } [text of cid from nodejs] Hello from nodejs
[closing...]
```

Accessed from nodejs helia to content on browser helia at first, the browser helia can access content on the nodejs helia.

## 2. Run halt case

```sh
$ node case-halt.mjs

[middle info URL] http://localhost:55314/
[peerId on nodejs] 12D3KooWLykYoddbySbRoZ6ajocCiSreKU4Pc9ZRGLrSPNm18gRM
[page server url] http://localhost:55346/index.html
(node:90594) [DEP0066] DeprecationWarning: OutgoingMessage.prototype._headers is deprecated
(Use `node --trace-deprecation ...` to show where the warning was created)
{ url: '', lineNumber: 4, columnNumber: 10 } [peerId on browser] 12D3KooWAUEY5s3DK9L9mxyNfDykybkwzQNktEtkVMmMxe1zGa5w
{ url: '', lineNumber: 4, columnNumber: 12 } [peer.id] 12D3KooWLykYoddbySbRoZ6ajocCiSreKU4Pc9ZRGLrSPNm18gRM
{ url: '', lineNumber: 5, columnNumber: 12 } [peer.multiaddrs.length] 6
{ url: '', lineNumber: 6, columnNumber: 46 } [peer.multiaddrs] /ip4/127.0.0.1/tcp/55312/p2p/12D3KooWMQM3PAYwKeK4n2MyE98LQZmFXRAENrXt8CV65Ej56KXY/p2p-circuit
{ url: '', lineNumber: 6, columnNumber: 46 } [peer.multiaddrs] /ip4/127.0.0.1/tcp/55313/ws/p2p/12D3KooWMQM3PAYwKeK4n2MyE98LQZmFXRAENrXt8CV65Ej56KXY/p2p-circuit
{ url: '', lineNumber: 6, columnNumber: 46 } [peer.multiaddrs] /ip4/127.0.0.1/tcp/55343
{ url: '', lineNumber: 6, columnNumber: 46 } [peer.multiaddrs] /ip4/192.168.10.6/tcp/55312/p2p/12D3KooWMQM3PAYwKeK4n2MyE98LQZmFXRAENrXt8CV65Ej56KXY/p2p-circuit
{ url: '', lineNumber: 6, columnNumber: 46 } [peer.multiaddrs] /ip4/192.168.10.6/tcp/55313/ws/p2p/12D3KooWMQM3PAYwKeK4n2MyE98LQZmFXRAENrXt8CV65Ej56KXY/p2p-circuit
{ url: '', lineNumber: 6, columnNumber: 46 } [peer.multiaddrs] /ip4/192.168.10.6/tcp/55343
{ url: '', lineNumber: 7, columnNumber: 12 } [peer.protocolss.length] 0
^C
```

The browser helia halt to access content on the nodejs helia at first.
