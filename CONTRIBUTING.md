# Contributing

## Contents of this file

### For contributors

- [Build and test locally](#build-and-test-locally)
- [Updating Changelog](#updating-changelog)

## Build and test locally

### Prerequisites

#### Tools

[pthon3](https://www.python.org/) needed by Molecule
[Molecule](https://molecule.readthedocs.io/en/latest/) is used for testing this
ansible role

Ubuntu prerequisite install:

```bash
sudo apt-get update
sudo apt install -y python3-pip libssl-dev tree
python3 -m pip install --user "molecule[ansible,lint,podman]"
```

##### Testing

```bash
molecule test
```

## Conventions to follow

[Ansible style guid](https://docs.ansible.com/ansible/latest/dev_guide/style_guide/index.html)

### PR Pipeline

The [GitHub Actions pipeline](.github/workflows/pr.yml) runs the integration
tests against every pull request. It follows the same steps laid out in the
[build and test locally](#build-and-test-locally) section.

## Updating Changelog

If you open a GitHub pull request on this repo, please update `CHANGELOG` to
reflect your contribution.

Add your entry under `Unreleased`, `Breaking changes`, `New features` or `Fixes`.

Internal changes to the project that are not part of the public API do not need
change log entries, for example fixing the CI build server.

These sections follow [semantic versioning](https://semver.org/), where:

- `Breaking changes` corresponds to a `major` (1.X.X) change.
- `New features` corresponds to a `minor` (X.1.X) change.
- `Fixes` corresponds to a `patch` (X.X.1) change.

See the [`CHANGELOG_TEMPLATE.md`](CHANGELOG_TEMPLATE.md) for an example for how
this looks.

## Releasing a new version

Each merge to `main` branch will create a GitHub release using semver 1.2.3
syntax.
