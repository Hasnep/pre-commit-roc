# pre-commit-roc

[Pre-commit](https://pre-commit.com/) hooks for the [Roc language](https://roc-lang.org/).

## Usage

Once you've [installed the Pre-commit tool](https://pre-commit.com/#install) and run `pre-commit install` in your project's repository, you can add the hooks to the `.pre-commit-config.yaml` file.
To pass additional arguments to the Roc CLI, use the `args` field.

```yaml
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/hasnep/pre-commit-roc
    rev: main
    hooks:
      - id: check
        name: Check Roc code
        args: [src/main.roc]
      - id: format
        name: Roc Check
      - id: test
        name: Run Roc tests
        args: [src/main.roc]
```

Then, whenever you make a commit, pre-commit will run `roc check`, `roc format` and `roc test` on your project.
