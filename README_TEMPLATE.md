# Your Project Name

Add some description here

## Prerequisites

* python 3.11 or later
* ...

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install foobar.

```bash
poetry install
```
## Developer Quick Start

In order to test frontend, you can start it separately:

```bash
cd webclient\app
npm install
npm start
```

## Usage

```python
import foobar

# returns 'words'
foobar.pluralize('word')

# returns 'geese'
foobar.pluralize('goose')

# returns 'phenomenon'
foobar.singularize('phenomena')
```
## Deployment

[Docker compose files](deployment/docker-compose) for environment setup and [helm chart](deployment/helm) can be found under [deployment](deployment). 

## Github Workflows and Versioning

The following Github Actions are available:

* [PR build](.github/workflows/pr-build.yml): Builds docker image for each pull request to main branch. Inside the docker image, `poetry install` and `poetry run python test.py` are executed, to compile and test entire python code.
* [Build and publish latest image](.github/workflows/build-publish-latest.yml): Manually executed action. Same like PR build. Additionally puts latest docker image to internal docker registry.
* [Create release](.github/workflows/create-release.yml): Manually executed action. Creates a github release with tag, docker image in internal docker registry, helm chart in chartmuseum by using and incrementing the version in pyproject.toml. Poetry is updating to next version by using "patch, minor and major" keywords. If you want to change to non-incremental version, set version in directly in pyproject.toml and execute create release afterwards.

## Dependabot Version Update

With [dependabot.yml](.github/dependabot.yml) a scheduled version update via Dependabot is configured. Dependabot creates a pull request if newer versions are available and the compilation is checked via PR build.

<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/ticket-number-AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request
