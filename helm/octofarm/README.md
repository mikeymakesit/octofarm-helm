# OctoFarm

Install the latest OctoFarm with MongoDB in a StatefulSet.

## Install

Install the chart, providing overrides for key chart values.
I *HIGHLY* recommend setting custom database credentials.

```bash
helm install \
  --namespace octofarm \
  --create-namespace \
  --set mongodb.config.rootUser=dbadmin \
  --set mongodb.config.rootPassword=412e-b17.basioermweq7d6 \
  octofarm octofarm
```

## Uninstall

So easy to remove:

```bash
helm uninstall octofarm
```

**NOTE** since it deploys as a StatefulSet the PersistentVolumeClaims
will *not* be deleted when you uninstall the Helm chart.  **This is
a feature**!  If you want to delete the volumes as well, just delete
the whole namespace:

```bash
kubectl delete ns octofarm
```

