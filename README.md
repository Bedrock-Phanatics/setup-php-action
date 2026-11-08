
<h1  align="center">Setup PHP Action</h1>

<p align="center">
  <a href="https://github.com/Bedrock-Phanatics/setup-php-action/actions">
    <img alt="Build Status" src="https://github.com/Bedrock-Phanatics/setup-php-action/workflows/build-test/badge.svg">
  </a>
</p>

A GitHub Action for setting up PHP and Composer in your CI workflows.

Built primarily for [Quark](https://github.com/Bedrock-Phanatics/Quark), this action downloads and installs prebuilt PHP binaries from [Bedrock-Phanatics/PHP-Binaries](https://github.com/Bedrock-Phanatics/PHP-Binaries/releases), making it easy to get a consistent PHP environment up and running.

While designed for Quark's own CI workflows, it can also be used by third-party plugins and projects running on GitHub Actions.

## Platform Support

- **Linux:** Supported
- **macOS:** Planned
- **Windows:** Planned

## Inputs

| Input | Required | Description |
|:------|:--------:|:------------|
| `php-version` | Yes | PHP version to install. Must be a full `major.minor.patch` version (e.g. `8.3.12`). Must be available in [PHP-Binaries](https://github.com/Bedrock-Phanatics/PHP-Binaries) (currently PHP `8.1` through `8.5`). |
| `install-path` | Yes | Directory where PHP and Composer will be installed (e.g. `./bin`). |
| `version-major` | No | Major version of [Quark](https://github.com/Bedrock-Phanatics/Quark) to build extensions for. Currently supports `5`. |

## Usage

Add the action to your GitHub Actions workflow:

```yaml
- name: Setup PHP
  uses: Bedrock-Phanatics/setup-php-action@main
  with:
    php-version: '8.4'
    install-path: './bin'
    version-major: '5'
```