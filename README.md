# api documentation for  [child-process-promise (v2.2.1)](https://github.com/patrick-steele-idem/child-process-promise#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-child-process-promise.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-child-process-promise) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-child-process-promise.svg)](https://travis-ci.org/npmdoc/node-npmdoc-child-process-promise)
#### Simple wrapper around the "child_process" module that makes use of promises

[![NPM](https://nodei.co/npm/child-process-promise.png?downloads=true)](https://www.npmjs.com/package/child-process-promise)

[![apidoc](https://npmdoc.github.io/node-npmdoc-child-process-promise/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-child-process-promise_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-child-process-promise/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-child-process-promise/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-child-process-promise/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Patrick Steele-Idem",
        "email": "pnidem@gmail.com"
    },
    "babel": {
        "presets": [
            "es2015"
        ],
        "plugins": [
            "check-es2015-constants",
            "transform-es2015-block-scoping"
        ]
    },
    "bugs": {
        "url": "https://github.com/patrick-steele-idem/child-process-promise/issues"
    },
    "dependencies": {
        "cross-spawn": "^4.0.2",
        "node-version": "^1.0.0",
        "promise-polyfill": "^6.0.1"
    },
    "description": "Simple wrapper around the \"child_process\" module that makes use of promises",
    "devDependencies": {
        "babel-cli": "^6.11.4",
        "babel-plugin-check-es2015-constants": "^6.8.0",
        "babel-plugin-transform-es2015-block-scoping": "^6.10.1",
        "babel-preset-es2015": "^6.13.2",
        "chai": "^3.5.0",
        "eslint": "^0.10.2",
        "jshint": "^2.9.1",
        "mocha": "^2.4.5"
    },
    "directories": {},
    "dist": {
        "shasum": "4730a11ef610fad450b8f223c79d31d7bdad8074",
        "tarball": "https://registry.npmjs.org/child-process-promise/-/child-process-promise-2.2.1.tgz"
    },
    "files": [
        "lib",
        "lib-es5",
        "Readme.md"
    ],
    "gitHead": "b324b76eeed3fa8c8e459e6b5b34c0d8b936b879",
    "homepage": "https://github.com/patrick-steele-idem/child-process-promise#readme",
    "keywords": [
        "child",
        "process",
        "promises"
    ],
    "license": "MIT",
    "main": "./index.js",
    "maintainers": [
        {
            "name": "psteeleidem",
            "email": "psteeleidem@ebay.com"
        },
        {
            "name": "pnidem",
            "email": "pnidem@gmail.com"
        }
    ],
    "name": "child-process-promise",
    "optionalDependencies": {},
    "publishConfig": {
        "registry": "http://registry.npmjs.org/"
    },
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/patrick-steele-idem/child-process-promise.git"
    },
    "scripts": {
        "lint": "eslint lib/*js test/*js",
        "mocha": "mocha --ui bdd --reporter spec ./test/",
        "prepublish": "babel lib --out-dir lib-es5",
        "test": "npm run mocha"
    },
    "version": "2.2.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module child-process-promise](#apidoc.module.child-process-promise)
1.  [function <span class="apidocSignatureSpan">child-process-promise.</span>ChildProcessPromise (executor)](#apidoc.element.child-process-promise.ChildProcessPromise)
1.  [function <span class="apidocSignatureSpan">child-process-promise.</span>exec ()](#apidoc.element.child-process-promise.exec)
1.  [function <span class="apidocSignatureSpan">child-process-promise.</span>execFile ()](#apidoc.element.child-process-promise.execFile)
1.  [function <span class="apidocSignatureSpan">child-process-promise.</span>fork (modulePath, args, options)](#apidoc.element.child-process-promise.fork)
1.  [function <span class="apidocSignatureSpan">child-process-promise.</span>spawn (command, args, options)](#apidoc.element.child-process-promise.spawn)
1.  object <span class="apidocSignatureSpan">child-process-promise.</span>ChildProcessPromise.prototype

#### [module child-process-promise.ChildProcessPromise](#apidoc.module.child-process-promise.ChildProcessPromise)
1.  [function <span class="apidocSignatureSpan">child-process-promise.</span>ChildProcessPromise (executor)](#apidoc.element.child-process-promise.ChildProcessPromise.ChildProcessPromise)

#### [module child-process-promise.ChildProcessPromise.prototype](#apidoc.module.child-process-promise.ChildProcessPromise.prototype)
1.  [function <span class="apidocSignatureSpan">child-process-promise.ChildProcessPromise.prototype.</span>fail (onRejected)](#apidoc.element.child-process-promise.ChildProcessPromise.prototype.fail)



# <a name="apidoc.module.child-process-promise"></a>[module child-process-promise](#apidoc.module.child-process-promise)

#### <a name="apidoc.element.child-process-promise.ChildProcessPromise"></a>[function <span class="apidocSignatureSpan">child-process-promise.</span>ChildProcessPromise (executor)](#apidoc.element.child-process-promise.ChildProcessPromise)
- description and source-code
```javascript
class ChildProcessPromise extends Promise {
    constructor(executor) {
        var resolve;
        var reject;

        super((_resolve, _reject) => {
            resolve = _resolve;
            reject = _reject;

            if (executor) {
                executor(resolve, reject);
            }
        });

        this._cpResolve = resolve;
        this._cpReject = reject;
        this.childProcess = undefined;
    }

    progress(callback) {
        process.nextTick(() => {
            callback(this.childProcess);
        });

        return this;
    }

    then(onFulfilled, onRejected) {
        var newPromise = super.then(onFulfilled, onRejected);
        newPromise.childProcess = this.childProcess;
        return newPromise;
    }

    catch(onRejected) {
        var newPromise = super.catch(onRejected);
        newPromise.childProcess = this.childProcess;
        return newPromise;
    }

    done() {
        this.catch((e) => {
            process.nextTick(() => {
                throw e;
            });
        });
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.child-process-promise.exec"></a>[function <span class="apidocSignatureSpan">child-process-promise.</span>exec ()](#apidoc.element.child-process-promise.exec)
- description and source-code
```javascript
function exec() {
    return doExec('exec', arguments);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.child-process-promise.execFile"></a>[function <span class="apidocSignatureSpan">child-process-promise.</span>execFile ()](#apidoc.element.child-process-promise.execFile)
- description and source-code
```javascript
function execFile() {
    return doExec('execFile', arguments);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.child-process-promise.fork"></a>[function <span class="apidocSignatureSpan">child-process-promise.</span>fork (modulePath, args, options)](#apidoc.element.child-process-promise.fork)
- description and source-code
```javascript
function fork(modulePath, args, options) {
    return doSpawn(child_process.fork, modulePath, args, options);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.child-process-promise.spawn"></a>[function <span class="apidocSignatureSpan">child-process-promise.</span>spawn (command, args, options)](#apidoc.element.child-process-promise.spawn)
- description and source-code
```javascript
function spawn(command, args, options) {
    return doSpawn(crossSpawn, command, args, options);
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.child-process-promise.ChildProcessPromise"></a>[module child-process-promise.ChildProcessPromise](#apidoc.module.child-process-promise.ChildProcessPromise)

#### <a name="apidoc.element.child-process-promise.ChildProcessPromise.ChildProcessPromise"></a>[function <span class="apidocSignatureSpan">child-process-promise.</span>ChildProcessPromise (executor)](#apidoc.element.child-process-promise.ChildProcessPromise.ChildProcessPromise)
- description and source-code
```javascript
class ChildProcessPromise extends Promise {
    constructor(executor) {
        var resolve;
        var reject;

        super((_resolve, _reject) => {
            resolve = _resolve;
            reject = _reject;

            if (executor) {
                executor(resolve, reject);
            }
        });

        this._cpResolve = resolve;
        this._cpReject = reject;
        this.childProcess = undefined;
    }

    progress(callback) {
        process.nextTick(() => {
            callback(this.childProcess);
        });

        return this;
    }

    then(onFulfilled, onRejected) {
        var newPromise = super.then(onFulfilled, onRejected);
        newPromise.childProcess = this.childProcess;
        return newPromise;
    }

    catch(onRejected) {
        var newPromise = super.catch(onRejected);
        newPromise.childProcess = this.childProcess;
        return newPromise;
    }

    done() {
        this.catch((e) => {
            process.nextTick(() => {
                throw e;
            });
        });
    }
}
```
- example usage
```shell
n/a
```



# <a name="apidoc.module.child-process-promise.ChildProcessPromise.prototype"></a>[module child-process-promise.ChildProcessPromise.prototype](#apidoc.module.child-process-promise.ChildProcessPromise.prototype)

#### <a name="apidoc.element.child-process-promise.ChildProcessPromise.prototype.fail"></a>[function <span class="apidocSignatureSpan">child-process-promise.ChildProcessPromise.prototype.</span>fail (onRejected)](#apidoc.element.child-process-promise.ChildProcessPromise.prototype.fail)
- description and source-code
```javascript
catch(onRejected) {
    var newPromise = super.catch(onRejected);
    newPromise.childProcess = this.childProcess;
    return newPromise;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
