# Deploy

## Build app

Run a local production-optimized build.

```sh
$ yarn build
```


## Release

This will run checks and tests, increment the tag version and push the new tagged commit.

```sh
$ yarn version minor
```


## Deploy pipeline

This project will run checks and build steps on [GitHub Actions](https://github.com/features/actions) on every commit or push on any branch.

See the [workflow](/.github/workflows/main.yml) config file.

See results on the [Actions](https://github.com/MichaelCurrin/corruption-calculator/actions/) tab.
