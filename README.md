# pre-commit-roc

[Pre-commit](https://pre-commit.com/) hooks for the [Roc language](https://roc-lang.org/).

## Usage

Assuming you've [installed the Pre-commit tool](https://pre-commit.com/#install) and run `pre-commit install` in your project's repository, you can add the hooks to the `.pre-commit-config.yaml` file.

```yaml
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/hasnep/pre-commit-roc
    rev: main
    hooks:
      - id: check
      - id: format
      - id: test
```

Then, whenever you commit, pre-commit will run `roc check`, `roc format` and `roc test` on your project.

To pass additional arguments to the Roc CLI, use the `args` field.
For example, to run `roc glue` on a file called `a.roc` to generate `b.rs`, use

```yaml
# .pre-commit-config.yaml
repos:
  - repo: https://github.com/hasnep/pre-commit-roc
    rev: main
      - id: glue
        args: ["main.roc", "main.rs"]
```
