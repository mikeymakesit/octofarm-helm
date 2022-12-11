# OctoFarm on Kubernetes

This project offers a Helm chart to install OctoFarm
on your Kubernetes cluster.

## Quick start

```bash
helm upgrade --install \
  --namespace octofarm \
  --set mongodb.config.rootPassword=DEFINE_NEW_PASSWORD_HERE
```

## Build a custom Docker image

If you want to roll a test image, download the source code and
run the following to build the image and push it to Docker Hub:

```bash
docker build -t dockerbrony/octofarm:1.8.0-beta.3 .
docker push dockerbrony/octofarm:1.8.0-beta.3
helm upgrade --install \
  --namespace octofarm \
  --set octofarm.image=dockerbrony/octofarm:1.8.0-beta.3 octofarm
```

## Further reading

See helm/octofarm/README.md for more info.

