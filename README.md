# Open WebUI Helm Charts
Helm charts for the [Open WebUI](https://github.com/open-webui/open-webui) application.

## Why was this chart forked
This chart was forked from the [open-webui/helm-charts](https://github.com/open-webui/helm-charts) repo
in order to enable using `volumeClaimTemplates` for multiple replicas

This chart was released using the [helm/chart-releaser](https://github.com/helm/chart-releaser) tool

## How to release a new version
1. Make changes to the chart in either a feature branch or the main branch
2. Make sure that you have the `chart-releaser` tool installed
3. Run the following commands to create a new release

```bash
cr package charts/open-webui
cr upload --owner tamu-edu --git-repo open-webui-helm-charts --packages-with-index --token <your PAT>
cr index --owner tamu-edu --git-repo open-webui-helm-charts --packages-with-index --index-path .  --token <your PAT> --push
```

The above will publish the correct templates and index files to a `gh-pages` branch of the repo
and publish it to github pages

## How to use the release
Use a `repository` value of `https://tamu-edu.github.io/open-webui-helm-charts/` 

Use a `chart` name of `open-webui`

Use a `version` from the repo such as `15.20.1`
