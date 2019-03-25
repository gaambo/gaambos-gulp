# Gaambos Gulp

A gulpfile.js boilerplate used in my WordPress boilerplates and projects.
Originally built for WordPress projects but can be used with any web project.

## Requirements

The library is built in modern JavaScript (using ES6+) and therefore best used with Gulp 4 (and as `gulpfile.babel.js` to use ES6).

## Installation

To use it in your project follow these steps:

1. Copy `gulpfile.babel.js` into your project.
2. Copy **`dependencies`** of `package.json` into your `package.json`s **`devDependencies`**.
3. Run `npm install`
4. Setup a `.babelrc` or `babel.config.js` in your project and configure the `preset-env` as used preset so the ES6 gulpfile gets transpiled.

## Usage

The gulpfile exports all tasks as ES6 exports, just as Gulp recommends.

### Configuration

You can either write the configuration inline or import from a file. To run the pre-defined tasks you need at least the configuration that's in the `gulpfile` right now.

### Tasks

This are the tasks exported:

- `scripts`: Concatenate and compiles scripts (via [babel](https://babeljs.io/)), minifies/uglifies scripts via [gulp-uglify](https://github.com/terinjokes/gulp-uglify), adds `.min` suffix and adds sourcemaps.
- `styles`: Compiles and autoprefixes (via [gulp-autoprefixer](https://github.com/sindresorhus/gulp-autoprefixer)) styles, minifies/uglifies styles via [gulp-uglifycss](https://github.com/ubirak/gulp-uglifycss), adds `.min` suffix and adds sourcemaps.
- `images`: Optimizes Images via [imagemin](https://github.com/imagemin/imagemin).
- `translate`: Generates pot files for WordPress .php files via [gulp-wp-pot](https://github.com/rasmusbe/gulp-wp-pot).
- `clean`: Deletes all files in the dist directory.
- `copyOtherFiles`: Copies additional files (like fonts, favicons,...) into the dist directory. See function comment/source for information how to configure.
- `build`: Runs `clean`, then `copyOtherFiles`, then (in parallel) `scripts`, `styles`, `images`, `translate`.
- `development`/default: Runs `build` and watches the CSS-, JS- and images-source directory for changes and runs the according tasks.

## Development

Contribution to this package is welcome. Just clone the repository, install all dependencies via npm and develop. There's no transpiling/compiling used.
ESLint is used with airbnb and prettier configuration.
