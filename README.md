# Batch steps Buildkite plugin

Run a large number of cloned steps in a configurable batch size

# Background

A common requirement at Culture Amp is to have a series of steps that are repeated (either on demand or automatically) by environment. Building on the functionality offered by the [step-templates](https://github.com/cultureamp/step-templates-buildkite-plugin) plugin, we sometimes want to dynamically generate those fragments to run the same step a very large number of times with different parameters.

# Example:

Given the following example:

```yaml

steps:
  - plugins:
      - cultureamp/batch-steps#v0.1.0:
          step-template: deploy-steps.yml
          batch-size: 8
          variable-file: selection-template.yml
          variable-name: REPLACE_THIS

```

## Developing

**Before** opening a pull request, run the tests. You may have to update the tests depending on your proposed change(s).

To run the tests:

```shell
docker-compose run --rm tests
```

You'll also want to run the linter:

```shell
docker-compose run --rm lint
```
