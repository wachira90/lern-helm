# HELM COMMAND

## CREATE CHART

```
helm create company
```

## EDIT VALUE

```yml
company\values.yaml
repository: docker.io/library/nginx

ingress:
  enabled: true

company\Chart.yaml
appVersion: "1.25.1"
```

## TEST RUN

```
helm install fda company --dry-run --debug
```

## INSTALL 

```
helm install fda company --namespace test
```

## UNINSTALL

```
helm uninstall fda --namespace test
```

## APPLY CONFIG WHEN EDIT

```
helm upgrade fda company --namespace test
```

## GENERATE YAML FILE

```
helm template company
#OR
helm template company > file.yaml
```


