jest mirror
================

Mirror of jest package for pre-commit.

For pre-commit: see https://github.com/pre-commit/pre-commit

For jest: see https://jestjs.io/


### Using jest with pre-commit

Add this to your `.pre-commit-config.yaml`:

```yaml
-   repo: https://github.com/hato1883/mirrors-jest-custom
    rev: ''  # Use the sha / tag you want to point at
    hooks:
    -   id: jest
```

When using plugins with `jest` you'll need to declare them under
`additional_dependencies`. For example:

```yaml
-   repo: https://github.com/hato1883/mirrors-jest-custom
    rev: ''  # Use the sha / tag you want to point at
    hooks:
    -   id: jest
        additional_dependencies:
        -   ...
```

By default only `*.js` files are taken into consideration.
If you want to use jest on TypeScript codebases you need
to start from this template:

```yaml
-   repo: https://github.com/hato1883/mirrors-jest-custom
    rev: ''  # Use the sha / tag you want to point at
    hooks:
    -   id: jest
        files: \.[jt]sx?$  # *.js, *.jsx, *.ts and *.tsx
        types: [file]
```
