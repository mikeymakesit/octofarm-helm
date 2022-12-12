# OctoFarm on Kubernetes

Install [OctoFarm](https://github.com/OctoFarm/OctoFarm) on your Kubernetes
cluster with this handy dandy Helm chart.

## Quick start

```bash
helm upgrade --install \
  --namespace octofarm \
  --set mongodb.config.rootPassword=DEFINE_NEW_PASSWORD_HERE
```

## Build a custom Docker image

To roll a test OctoFarm image, download the OctoFarm source code and
run something like the following to build an image and push it to your repo:

```bash
git clone https://github.com/OctoFarm/OctoFarm.git
cd OctoFarm
git checkout tags/v1.8.0-beta.3 -b betas/beta-1.8.0
docker build -t myrepo/octofarm:1.8.0-beta.3 .
docker push myrepo/octofarm:1.8.0-beta.3
cd /path/to/this_project/helm
helm upgrade --install \
  --namespace octofarm \
  --set octofarm.image=myrepo/octofarm:1.8.0-beta.3 octofarm
```

## Further reading

See [the Helm chart's README](helm/octofarm/README.md) for more info.

<https://github.com/OctoFarm/OctoFarm>

