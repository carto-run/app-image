# app-image

## Creating the Workload

```
tanzu apps workload create app-image \
  --namespace dev \
  --git-branch main \
  --git-repo https://github.com/carto-run/app-image \
  --label apps.tanzu.vmware.com/has-tests=true \
  --label app.kubernetes.io/part-of=app-image \
  --type web \
  --yes
```

## Logs

```
tanzu apps workload tail app-image
```

## Configuration

| Item            | Config                                                                                |
| --------------- | ------------------------------------------------------------------------------------- |
| Scan Policy     | [default](resources/scan-policy.yaml)                                                 |
| Pipeline        | [developer-defined-tekton-pipeline](resources/developer-defined-tekton-pipeline.yaml) |
| tap-values.yaml | na                                                                                    |
| Supply Chain    | source-test-scan-to-url                                                               |

