# HELM COMMAND

## DOWNLOAD 

https://github.com/helm/helm/releases

```
helm version 

helm create company
```

## EDIT MAIN CONFIG

nano company/values.yaml

```yml
image:
  repository: public.ecr.aws/nginx/nginx
  tag: "1.27.3"

serviceAccount:
  create: false

ingress:
  enabled: true
  className: "public"
  hosts:
    - host: develop.192-168-1-10.nip.io

```

## EDIT VERSION

nano example/Chart.yaml

```yml
appVersion: "1.0.0"
```


# DELETE FILE

```sh
rm company/templates/tests/test-connection.yaml
```

## TEST RUN

```sh
helm install fda company --dry-run --debug
```

## INSTALL 

```sh
helm install fda company -n test
```

## UNINSTALL

```sh
helm uninstall fda -n test
```

## APPLY CONFIG WHEN EDIT

```sh
helm upgrade fda company -n test
```

## GENERATE YAML FILE

```sh
helm template fda company
```

### OR

```sh
helm template fda company > file.yaml
```

## USE CASE 

### DATA

```
companyname : ekyc
service : landing
service : web
service : api
```

### COMMAND 

```sh
helm create landing

helm create web

helm create api

helm template ekyc landing

helm template ekyc web

helm template ekyc api

helm install ekyc landing -n test

helm install ekyc web -n test

helm install ekyc api -n tes

```
