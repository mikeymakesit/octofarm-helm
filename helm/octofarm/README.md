# OctoFarm

This Helm chart installs the latest OctoFarm and a required MongoDB instance
as a StatefulSet.

## Install

Example of installing the chart with default values:

```bash
helm install --namespace octofarm --create-namespace octofarm octofarm/
```

Here's how you're more likely to install the chart, providing
overrides for key chart values.  I *HIGHLY* recommend setting
custom database username and password, like so:

```bash
helm install \
  --namespace octofarm \
  --create-namespace \
  --set mongodb.config.rootUser=dbadmin \
  --set mongodb.config.rootPassword=412e-b17.basioermweq7d6 \
  octofarm octofarm
```

## Uninstall

Helm charts are so easy to remove:

```bash
helm uninstall octofarm
```

**NOTE** that since it deploys as a StatefulSet the PersistentVolumeClaims
will not be deleted when you uninstall the Helm chart.  This is a feature!
If you want to delete the volumes as well, it's easiest to just delete
the whole namespace:

```bash
kubectl delete ns octofarm
```

