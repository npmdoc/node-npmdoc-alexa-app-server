# api documentation for  [alexa-app-server (v3.0.1)](https://github.com/alexa-js/alexa-app-server#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-alexa-app-server.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-alexa-app-server) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-alexa-app-server.svg)](https://travis-ci.org/npmdoc/node-npmdoc-alexa-app-server)
#### A web server module for Alexa (Amazon Echo) apps (skills) using Node.js, Express, and alexa-app.

[![NPM](https://nodei.co/npm/alexa-app-server.png?downloads=true)](https://www.npmjs.com/package/alexa-app-server)

[![apidoc](https://npmdoc.github.io/node-npmdoc-alexa-app-server/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-alexa-app-server_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-alexa-app-server/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-alexa-app-server/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-alexa-app-server/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Matt Kruse"
    },
    "bugs": {
        "url": "https://github.com/alexa-js/alexa-app-server/issues"
    },
    "dependencies": {
        "alexa-app": "^3.2.0",
        "bluebird": "^3.4.7",
        "body-parser": "~1.16.0",
        "ejs": "~2.5.5",
        "express": "~4.14.1",
        "hotswap": "^1.1.0",
        "lodash.defaults": "^4.2.0"
    },
    "description": "A web server module for Alexa (Amazon Echo) apps (skills) using Node.js, Express, and alexa-app.",
    "devDependencies": {
        "chai": "^3.5.0",
        "coveralls": "^2.11.15",
        "danger": "0.11.4",
        "istanbul": "0.4.5",
        "mocha": "^3.2.0",
        "sinon": "^1.17.7",
        "sinon-chai": "^2.8.0",
        "supertest": "^3.0.0",
        "tcp-port-used": "0.1.2"
    },
    "directories": {},
    "dist": {
        "shasum": "5fe1cc4b9bda291a7da795f2bcb862415259082f",
        "tarball": "https://registry.npmjs.org/alexa-app-server/-/alexa-app-server-3.0.1.tgz"
    },
    "gitHead": "6aac5665d4b1f3f82444cc10fe79d249b0787829",
    "homepage": "https://github.com/alexa-js/alexa-app-server#readme",
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "dblock",
            "email": "dblock@dblock.org"
        },
        {
            "name": "mkruse",
            "email": "github@mattkruse.com"
        },
        {
            "name": "rickwargo",
            "email": "npm@epicminds.com"
        },
        {
            "name": "tejashah88",
            "email": "tejashah88@gmail.com"
        }
    ],
    "name": "alexa-app-server",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/alexa-js/alexa-app-server.git"
    },
    "scripts": {
        "coverage": "istanbul cover ./node_modules/.bin/_mocha -- -R spec",
        "coverage_local": "istanbul cover node_modules/mocha/bin/_mocha",
        "danger": "danger",
        "test": "mocha"
    },
    "version": "3.0.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module alexa-app-server](#apidoc.module.alexa-app-server)
1.  [function <span class="apidocSignatureSpan">alexa-app-server.</span>start (config)](#apidoc.element.alexa-app-server.start)
1.  object <span class="apidocSignatureSpan">alexa-app-server.</span>utils

#### [module alexa-app-server.utils](#apidoc.module.alexa-app-server.utils)
1.  [function <span class="apidocSignatureSpan">alexa-app-server.utils.</span>isValidDirectory (dir)](#apidoc.element.alexa-app-server.utils.isValidDirectory)
1.  [function <span class="apidocSignatureSpan">alexa-app-server.utils.</span>isValidFile (file)](#apidoc.element.alexa-app-server.utils.isValidFile)
1.  [function <span class="apidocSignatureSpan">alexa-app-server.utils.</span>normalizeApiPath (apiPath)](#apidoc.element.alexa-app-server.utils.normalizeApiPath)
1.  [function <span class="apidocSignatureSpan">alexa-app-server.utils.</span>readFile (file)](#apidoc.element.alexa-app-server.utils.readFile)
1.  [function <span class="apidocSignatureSpan">alexa-app-server.utils.</span>readJsonFile (file)](#apidoc.element.alexa-app-server.utils.readJsonFile)



# <a name="apidoc.module.alexa-app-server"></a>[module alexa-app-server](#apidoc.module.alexa-app-server)

#### <a name="apidoc.element.alexa-app-server.start"></a>[function <span class="apidocSignatureSpan">alexa-app-server.</span>start (config)](#apidoc.element.alexa-app-server.start)
- description and source-code
```javascript
start = function (config) {
  var appServerInstance = new appServer(config);
  appServerInstance.start();
  return appServerInstance;
}
```
- example usage
```shell
...
'''

## Usage

'''javascript
var AlexaAppServer = require('alexa-app-server');

var instance = AlexaAppServer.start({
  server_root: __dirname,     // Path to root
  public_html: "public_html", // Static content
  app_dir: "apps",            // Location of alexa-app modules
  app_root: "/alexa/",        // Service root
  port: 8080                  // Port to use
});
...
```



# <a name="apidoc.module.alexa-app-server.utils"></a>[module alexa-app-server.utils](#apidoc.module.alexa-app-server.utils)

#### <a name="apidoc.element.alexa-app-server.utils.isValidDirectory"></a>[function <span class="apidocSignatureSpan">alexa-app-server.utils.</span>isValidDirectory (dir)](#apidoc.element.alexa-app-server.utils.isValidDirectory)
- description and source-code
```javascript
isValidDirectory = function (dir) {
  return fs.existsSync(dir) && fs.statSync(dir).isDirectory();
}
```
- example usage
```shell
...
var alexaRouter = express.Router();

var normalizedRoot = utils.normalizeApiPath(root);
self.express.use(normalizedRoot, alexaRouter);

var app_directories = function(srcpath) {
  return fs.readdirSync(srcpath).filter(function(file) {
    return utils.isValidDirectory(path.join(srcpath, file));
  });
};

app_directories(app_dir).forEach(function(dir) {
  var package_json = path.join(app_dir, dir, "package.json");
  if (!utils.isValidFile(package_json)) {
    self.error("   package.json not found in directory " + dir);
...
```

#### <a name="apidoc.element.alexa-app-server.utils.isValidFile"></a>[function <span class="apidocSignatureSpan">alexa-app-server.utils.</span>isValidFile (file)](#apidoc.element.alexa-app-server.utils.isValidFile)
- description and source-code
```javascript
isValidFile = function (file) {
  return fs.existsSync(file) && fs.statSync(file).isFile();
}
```
- example usage
```shell
...
return fs.readdirSync(srcpath).filter(function(file) {
  return utils.isValidDirectory(path.join(srcpath, file));
});
    };

    app_directories(app_dir).forEach(function(dir) {
var package_json = path.join(app_dir, dir, "package.json");
if (!utils.isValidFile(package_json)) {
  self.error("   package.json not found in directory " + dir);
  return;
}

var pkg = utils.readJsonFile(package_json);
if (!pkg || !pkg.main || !pkg.name) {
  self.error("   failed to load " + package_json);
...
```

#### <a name="apidoc.element.alexa-app-server.utils.normalizeApiPath"></a>[function <span class="apidocSignatureSpan">alexa-app-server.utils.</span>normalizeApiPath (apiPath)](#apidoc.element.alexa-app-server.utils.normalizeApiPath)
- description and source-code
```javascript
normalizeApiPath = function (apiPath) {
  return path.posix.normalize(path.posix.join('/', apiPath));
}
```
- example usage
```shell
...
  hotswap.on('error', errorCallback);

  // load application modules
  self.load_apps = function(app_dir, root) {
// set up a router to hang all alexa apps off of
var alexaRouter = express.Router();

var normalizedRoot = utils.normalizeApiPath(root);
self.express.use(normalizedRoot, alexaRouter);

var app_directories = function(srcpath) {
  return fs.readdirSync(srcpath).filter(function(file) {
    return utils.isValidDirectory(path.join(srcpath, file));
  });
};
...
```

#### <a name="apidoc.element.alexa-app-server.utils.readFile"></a>[function <span class="apidocSignatureSpan">alexa-app-server.utils.</span>readFile (file)](#apidoc.element.alexa-app-server.utils.readFile)
- description and source-code
```javascript
readFile = function (file) {
  return fs.readFileSync(file, 'utf8');
}
```
- example usage
```shell
...
      if (self.config.privateKey != undefined && self.config.certificate != undefined && self.config.httpsPort != undefined) {
        var sslCertRoot = path.join(self.config.server_root, 'sslcert');
        var privateKeyFile = path.join(sslCertRoot, self.config.privateKey);
        var certificateFile = path.join(sslCertRoot, self.config.certificate);
        var chainFile = (self.config.chain != undefined) ? path.join(sslCertRoot, self.config.chain) : undefined;

        if (utils.isValidFile(privateKeyFile) && utils.isValidFile(certificateFile)) {
var privateKey = utils.readFile(privateKeyFile);
var certificate = utils.readFile(certificateFile);

var chain = undefined;
if (chainFile != undefined) {
  if (utils.isValidFile(chainFile)) {
    chain = utils.readFile(chainFile);
  } else {
...
```

#### <a name="apidoc.element.alexa-app-server.utils.readJsonFile"></a>[function <span class="apidocSignatureSpan">alexa-app-server.utils.</span>readJsonFile (file)](#apidoc.element.alexa-app-server.utils.readJsonFile)
- description and source-code
```javascript
readJsonFile = function (file) {
  return JSON.parse(readFile(file));
}
```
- example usage
```shell
...
    app_directories(app_dir).forEach(function(dir) {
var package_json = path.join(app_dir, dir, "package.json");
if (!utils.isValidFile(package_json)) {
  self.error("   package.json not found in directory " + dir);
  return;
}

var pkg = utils.readJsonFile(package_json);
if (!pkg || !pkg.main || !pkg.name) {
  self.error("   failed to load " + package_json);
  return;
}

var main = fs.realpathSync(path.join(app_dir, dir, pkg.main));
if (!utils.isValidFile(main)) {
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
