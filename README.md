# setup-rails

This is a re-usable GitHub Actions workflow based on the post [Building a Rails CI pipeline with GitHub Actions](https://boringrails.com/articles/building-a-rails-ci-pipeline-with-github-actions/) by [Matt Swanson](https://github.com/swanson).

To use it, create a file in your repo at `.github/workflows/verify.yml`
containing:

```yaml
name: Verify
on: [push]

jobs:
  verify:
    uses: andyw8/setup-rails/.github/workflows/verify.yml@v1
    # uncomment to enable optional steps:
    #
    # with:
    #   brakeman: true
    #   bundler-audit: true
    #   rspec: true
```

If you're using a non-x86 machine for development (e.g. Apple M1), you'll need to update `Gemfile.lock` by running:

```
bundle lock --add-platform x86_64-linux
```

[Here is an example app](https://github.com/andyw8/setup-rails-example-app) which uses this workflow.

## Current Limitations

- Assumes postgres, no support for mysql or other databases
- Assumes RuboCop is present
- Assumes yarn, no support for npm
