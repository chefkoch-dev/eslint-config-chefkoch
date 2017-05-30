# eslint-config-chefkoch

This repository provides Chefkoch's shared eslint config (`.eslintrc.json`). The config is (for now) a simple extension of Airbnb's base package with a few opinionated overrides.

## Usage

```
yarn add eslint-config-airbnb-base eslint eslint-plugin-import
```

To use Chefkoch's eslint config, start by installing the required dependencies in your project with the command above (we strongly recommend you use `yarn` but you can also use `npm install <package…>`). Airbnb's config (and, by extension, ours) contains all of their ESLint rules, including ECMAScript 6+. It requires `eslint` and `eslint-plugin-import`.

Afterwards, download the `.eslintrc.json` file from this repository and place it in the root folder of your project.

### Use with gulp

If you lint your JS via a `gulp` task in your build step (recommended), `gulp-eslint` is also required. A simple task that lints all Javascript files in your local `/src/` folder looks like this:

```
gulp.task('lint', function() {
    return gulp.src(['./src/**/*.js'])
        .pipe(eslint())
        .pipe(eslint.format())
        .pipe(eslint.failAfterError());
});
```
