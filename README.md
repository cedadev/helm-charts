# helm-charts

This repository contains Helm charts distributed under `cedadev`.

The chart repository is built in the `docs` directory and served using Github pages.
This repository includes a Git `pre-commit` hook that will rebuild the repository
before each commit.

## Usage

To install the chart repository, just run:

```sh
helm repo add cedadev https://cedadev.github.io/helm-charts
```

The charts in this repository will then be available as `cedadev/<name>`.

## Developing

After cloning this repository, you must install the `pre-commit` hook to ensure
that the chart repository is built when you commit:

```sh
git clone git@github.com:cedadev/helm-charts.git
cd helm-charts
ln -s ../../.git-hooks/pre-commit .git/hooks/pre-commit
```

Once the `pre-commit` hook is installed, modify/add any charts you need, then
just add, commit and push using `git` as usual.
