# setup-rails

This is a re-usable GitHub Actions workflow based on the post [Building a Rails CI pipeline with GitHub Actions](https://boringrails.com/articles/building-a-rails-ci-pipeline-with-github-actions/) by [Matt Swanson](https://github.com/swanson).

Blog Post: [A GitHub Actions Rails CI Workflow in 5 lines](https://www.andywaite.com/2022/04/15/reusable-github-actions-rails-workflow.html)

To use it, create a file in your repo at `.github/workflows/verify.yml`
containing:

<!-- begin example -->
```yaml
name: Verify
on: [push]

jobs:
  verify:
    uses: andyw8/setup-rails/.github/workflows/verify.yml@v1
    # uncomment to enable options:
    #
    # with:
    #   brakeman: true
    #   bundler-audit: true
    #   rspec: true
    #   rubocop: true
```
<!-- end example -->

Alternatively, you can install with [RailsBytes](https://railsbytes.com/templates/VMys8A):

```
rails app:template LOCATION="https://railsbytes.com/script/VMys8A"
```

You'll to update `Gemfile.lock` by running:

```
bundle lock --add-platform x86_64-linux
```

[Here is an example app](https://github.com/andyw8/setup-rails-example-app) which uses this workflow.

## Current Limitations

- Assumes postgres, no support for mysql or other databases
- Assumes yarn, no support for npm
