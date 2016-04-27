# qiget
Proxied download tool over Qiniu Resource (Cloud) Storage.

## Install

    npm install --global qiget

## Command line usage

    qiget [options] <url>

    Options:

      -a, --access [key]   Specify access key, default to process.env.QIGET_ACCESS_KEY
      -s, --secret [key]   Specify secret key, default to process.env.QIGET_SECRET_KEY
      -b, --bucket [name]  Specify bucket name of storage, default to process.env.QIGET_BUCKET
      -h, --host [name]    Specify bucket hostname of storage, default to process.env.QIGET_HOST
      -d, --download       Download the file in storage after storing.
      -r, --remove         Remove the file in storage after downloading.

- When `--download` is set, the file content will be piped to process.stdout,
  otherwise the url in storage will be outputted
- `--remove` is only available with `--download`

## Node.js usage

```js
qiget = require('qiget')
qiget({
  url: "", // Remote URL
  access: "", // Access key
  secret: "", // Secret key
  bucket: "", // Bucket name
  host: "", // Host
}).then((url) => {
  // File is successfully stored in storage with `url`
}, (reason) => {
  // Boom!
})
```

## License

MIT
