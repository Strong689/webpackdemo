
# [webpack: bundle your assets](https://webpack.js.org/)

[webpack @github](https://github.com/webpack/webpack)

````bash
npm install --save-dev webpack
yarn add webpack --dev
```

UX
DX

https://www.git-tower.com/blog/git-cheat-sheet/

https://github.com/academind
https://academind.com/


## 1. Basic Demo

* initial project, without webpack
    access by : file:///Users/xyz/webpackdemo/index.html

* Add webpack & modify js & index.html files

````bash
npm init // first step package.json
npm install --save-dev webpack // develop dependency
npm run build  //last step
```

    - package.json. scripts

    "build": "webpack src/js/app.js dist/bundle.js",
    "build:prod": "webpack src/js/app.js dist/bundle.js -p"

    - dom-loader.js: export 
    - app.js: import {secretParagraph,secretButton} from './dom-loader';
    - index.html: <script src="dist/bundle.js"></script>

````bash
git init webpackdemo
cd webpackdemo
git add .
git commit -a -m "initial project, without webpack"
git commit src/js/app.js -m "modify toggleSecreteState->toggleSecretState"
git commit -a -m "Add webpack & modify js & index.html files"
git tag -a v1.0 525e9 -m  "demo version1.0 without webpack2, function works"

git status
git diff
git log
git show

npm run build
npm run build:prod
git tag -a v2.0 0cb7ea -m  "demo version2.0, running with webpack2"

git tag
git show v1.0
```

* [Webpack Dev Server](https://github.com/webpack/webpack-dev-server)

[issue http://127.0.0.1:8080/ vs http://localhost:8080/](https://github.com/webpack/webpack-dev-server/issues/183)

````bash
npm install --save-dev webpack-dev-server  
```
package.json, both works

    - work: "build": "webpack-dev-server --entry ./src/js/app.js --output-filename ./dist/bundle.js", //with error: net::ERR_EMPTY_RESPONSE
    - works: "build": "webpack-dev-server src/js/app.js dist/bundle.js", // no err
    
    "build": "webpack-dev-server --host localhost --port 3000 src/js/app.js dist/bundle.js",

