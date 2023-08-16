# HELM COMMAND

## CREATE CHART

```
helm create mychart
```

## EDIT VALUE

```yml
mychart\values.yaml
repository: docker.io/library/nginx

ingress:
  enabled: true

mychart\Chart.yaml
appVersion: "1.25.1"
```

## TEST RUN

```
helm install fda mychart --dry-run --debug
```

## INSTALL 

```
helm install fda mychart --namespace test
```

## UNINSTALL

```
helm uninstall fda --namespace test
```

## APPLY CONFIG WHEN EDIT

```
helm upgrade fda mychart --namespace test
```

## GENERATE YAML FILE

```
helm template mychart
#OR
helm template mychart > file.yaml
```


