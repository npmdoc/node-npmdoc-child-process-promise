# npmdoc-child-process-promise

#### api documentation for  [child-process-promise (v2.2.1)](https://github.com/patrick-steele-idem/child-process-promise#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-child-process-promise.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-child-process-promise) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-child-process-promise.svg)](https://travis-ci.org/npmdoc/node-npmdoc-child-process-promise)

#### Simple wrapper around the "child_process" module that makes use of promises

[![NPM](https://nodei.co/npm/child-process-promise.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/child-process-promise)

- [https://npmdoc.github.io/node-npmdoc-child-process-promise/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-child-process-promise/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-child-process-promise/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-child-process-promise/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-child-process-promise/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-child-process-promise/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Patrick Steele-Idem"
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
            "name": "psteeleidem"
        },
        {
            "name": "pnidem"
        }
    ],
    "name": "child-process-promise",
    "optionalDependencies": {},
    "publishConfig": {
        "registry": "http://registry.npmjs.org/"
    },
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



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
