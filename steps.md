# Step-by-step guide

[ARTICLE SOURCE](https://medium.com/@mattiaperi/create-a-public-helm-chart-repository-with-github-pages-49b180dbb417)

*Please keep in mind that following the instruction below, your Helm charts repository will be public.*

Create a new repository on your Github account (i.e. “service-helm”):

## Create robots.txt
I’d like to avoid bot crawling on my repository, so I add the following robots.txt file:
```bash
echo -e “User-Agent: *\nDisallow: /” > robots.txt
```

## Create a helm chart from scratch (or copy your own)

```bash
helm create service-helm
```

## Lint the chart
As a good habit, helm lint runs a series of tests to verify that
the chart is well-formed:

```bash
helm lint service-helm/*
```

## Create the Helm chart package
This command packages a chart into a versioned chart archive file. If a path is given, this will look at that path for a chart (which must contain a Chart.yaml file) and then package that directory.

```bash
helm package service-helm/*
```

