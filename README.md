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

## Styleguide

Airbnb has put a tremendous effort into documenting their _mostly reasonable approach to JavaScript_. We strongly recommend you check out [Airbnb's Javascript styleguide](https://github.com/airbnb/javascript) to discover the reasons behind the linting rules.

### Deviation from Airbnb in Chefkoch's config

There are only a few rules where we have decided to diverge from Airbnb with overrides:
* we indent with 4 spaces, not 2
* we allow property mutation on function parameters
* we allow the use of for…in loops
* we do not test against an arbitray maximum of characters per length but strive to solve readability issues through code reviews
