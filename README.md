# pre-commit-php-laravel

Pre-commit scripts appropiate for any laravel application.

# Setup

See (Adding pre-commit plugins to your project)[https://pre-commit.com/#adding-pre-commit-plugins-to-your-project]

# Supported Hooks

## Pest test

```yaml
- repo: https://github.com/larasense/pre-commit-php-laravel
  rev: 1.0.0
  hooks:
    - id: pest-test
```

It run Pest on a local environment

## Sail Pest test

```yaml
- repo: https://github.com/larasense/pre-commit-php-laravel
  rev: 1.0.0
  hooks:
    - id: pest-test-sail
```

It run Pest tests on a Sail environment.

# My recomended pre-commit config file

This repo is inspired by https://github.com/digitalpulp/pre-commit-php and it is meant to be an extention of it.

## Configuration file

```yaml
# .pre-commit-config.yaml

repos:
  - repo: https://github.com/digitalpulp/pre-commit-php.git
    rev: 1.4.0
    hooks:
      - id: php-stan
        pass_filenames: false
        args:
          - "--memory-limit=2G"
      - id: php-lint
  - repo: https://github.com/larasense/pre-commit-php-laravel
    rev: 1.0.0
    hooks:
      - id: pest-test-sail
```
