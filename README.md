# setup-rails

This is a re-usable GitHub Action based on the post [Building a Rails CI pipeline with GitHub Actions](https://boringrails.com/articles/building-a-rails-ci-pipeline-with-github-actions/) by @swanson.

Take a look at the example app for configuration details:

https://github.com/andyw8/setup-rails-example-app/blob/main/.github/workflows/verify.yaml

If you're using non x86 machine for development (e.g. Apple M1), you'll need to
update `Gemfile.lock` by running:

```
bundle lock --add-platform x86_64-linux
```
