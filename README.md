# Sprouts S2BS - (Static Site Build System)

## Introduction

Sprouts is an automated build system for static websites. It automates repetitive build tasks and provides `live browser reload` and `live test runner`.


## Installation

Download and unzip sprouts in an empty directory. Then open the terminal in the directory and run:
```bash
npm run sprouts
```

This modifies the `package.json` file using your input and installs the dependencies from it.

### Requirements

[`gulp-scss-lint`](https://www.npmjs.com/package/gulp-scss-lint) package requires Ruby and `scss_lint`.
```bash
gem install scss_lint
```


## Getting Started

### Sprouts workflow

Sprouts creates _development_ and _production_ builds. The _development_ build contains source maps for both the JavaScript and Sass files. The _production_ build is minified and supposed to be deployed.


### Sprouts commands

#### Development

To create a _development_ build and start a server at `http://localhost:3000`, execute:
```bash
npm run dev
```
Each time you save a source file in the `src` directory, the _development_ build updates and the browser reloads.


#### Testing

To start testing, execute:
```bash
npm test
```
The test runner starts and runs the tests each time the source files are changed.


#### Production

To create a _production_ build execute:
```bash
npm run build:prod
```


### Directory structure

```
.
├── builds
    ├── dev
    └── production
├── gulpfile.js
├── package.json
├── README.md
├── requirements
├── sprouts
└── src
    ├── fonts
    ├── img
    ├── index.html
    ├── js
    │   ├── compiledTemplates
    │   ├── lib
    │   ├── main.js
    │   └── test
    │       └── demo.test.js
    └── scss
        ├── styles.scss
        └── vendors
```

`builds` &mdash; directory contains the development and production builds. __The contents of the `builds` directory is deleted automatically.__

`gulpfile.js` &mdash; directory contains the gulp tasks.

`src/` &mdash; directory is for your code and assets.

`src/js/lib` &mdash; directory for your `js` modules.

`src/js/test` &mdash; directory for `js` tests. File names should end in `.test.js`.

`src/scss` &mdash; directory is for `sass` and `scss` styles. The `vendors` directory is for third party libraries, like Bootstrap.

`requirements` &mdash; directory contains a template requirements file for your app/website.


## Built With

Sprouts uses:
* Automation:
  * [gulp](https://gulpjs.com/) to automate the builds and asset management;
* JS Compilation:
  * [browserify](http://browserify.org/) to bundle the `js` files;
* Sass Compilation:
  * [gulp-sass](https://github.com/dlmanning/gulp-sass)
* Testing:
  * [karma](https://karma-runner.github.io/1.0/index.html) to run tests;
  * [mocha](https://mochajs.org/) as a test framework;
  * [chai](http://chaijs.com/) assertion library;
* Live Server:
  * [browser-sync](https://www.browsersync.io/) for live server;
* Linting:
  * See `package.json` for a complete list.


## Author

Dimitar Danov


## License

This project is licensed under the MIT License - see the LICENSE file for details.


## Acknowledgements

Sprouts is influenced [gulp-starter (blendid)](https://github.com/vigetlabs/blendid), [article](https://www.viget.com/articles/gulp-browserify-starter-faq).
