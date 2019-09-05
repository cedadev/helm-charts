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

## Adding charts

After cloning this repository, you must install the `pre-commit` hook to ensure
that the chart repository is built when you commit:

```sh
git clone git@github.com:cedadev/helm-charts.git
cd helm-charts
ln -s ../../.git-hooks/pre-commit .git/hooks/pre-commit
```

Once the `pre-commit` hook is installed, modify/add any charts you need, then
just add, commit and push using `git` as usual. The `pre-commit` hook will
automatically run `helm package` on any folders with a `Chart.yaml` inside and
then rebuild the index.

### Adding a chart from another repository

If your Helm chart lives in another Git repository but you wish to distribute it via
the `cedadev` Helm repository, you can just package the chart into the `docs` directory
by running the following command:

```sh
helm package -u -d /path/to/cedadev/helm-charts/docs /path/to/your/chart
```

### Adding a pre-existing chart

If all you want to do is add a pre-existing chart from another Helm repository
to the `cedadev` repository, you just need to download the packaged chart to the
`docs` directory:

```sh
helm fetch -d /path/to/cedadev/helm-charts/docs repo/chartname
```
