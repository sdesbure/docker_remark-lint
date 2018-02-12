# Remark Lint Docker

remark-lint - <https://github.com/remarkjs/remark-lint>

Latest remark-lint release in node embedded into this docker.

Used to perform markdown linting into gitlab ci runner.

## Docker image

[![](https://images.microbadger.com/badges/image/sdesbure/remark-lint.svg)](https://microbadger.com/images/sdesbure/remark-lint "Get your own image badge on microbadger.com")
[![](https://images.microbadger.com/badges/version/sdesbure/remark-lint.svg)](https://microbadger.com/images/sdesbure/remark-lint "Get your own version badge on microbadger.com")

## How to use

### Pull image

```
docker pull sdesbure/remark-lint
```

## Run container

Per default, the docker will give you the version number of remark-lint.

If you want to do linting you'll have to run a specific command:

```
docker run --rm -v <path for playbook folder to lint>:/code sdesbure/remark-lint node_modules/.bin/remark  yourFile.md
```

## In gitlab ci runner

Here's an example of a working configuration (that have a `lint` stage):

```
markdown_linting:
  stage: lint
  image: sdesbure/remark-lint
  script:
    - remark-lint *.md
```
