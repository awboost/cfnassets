# @awboost/cfnassets

Build asset zip packages for deployment.

## Quick Start

You need an assets config file:

```jsonc
// cfnassets.config.json
{
  "api": {
    "type": "rollup",
    "options": {
      "entrypoint": "./core/lib/api/lambda.js",
      "install": ["source-map-support"],
      "packageFilePath": "package.json",
      "packageInstallImage": "node:16-slim",
      "packageLockPath": "package-lock.json"
    }
  },
  "app-client": {
    "type": "content",
    "options": {
      "source": "apps/client/build"
    }
  }
}
```

Then run:

```
cfnassets build --config cfnassets.config.json
```
