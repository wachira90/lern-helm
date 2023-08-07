# lern-helm

## download

https://github.com/helm/helm/releases

Helm command reference

Helm provides many commands for managing charts and Helm repositories. This list shows examples of the more common commands. After you configure a connection, you must add the --tls option to Helm commands that access the server through Tiller.

## Install Tiller:

```sh
$ helm init
```
## Create a chart:

```sh
$ helm create <chart>
```

## List the repositories:

```sh
$ helm repo list
```

## Search for a chart:

```sh
$ helm search <keyword>
```

## Get information about a chart:

```sh
$ helm inspect <chart>
```

## Deploy a chart (creates a release):

```sh
$ helm install <chart>
```

## List all releases:

```sh
$ helm list --all
```

## Get the status of a release:

```sh
$ helm status <release>
```

## Get the details about a release:

```sh
$ helm get <release>
```

## Upgrade a release:

```sh
$ helm upgrade <release> <chart>
```

## Roll back a release:

```sh
$ helm rollback <release> <revision>
```

## Delete a release:

```sh
$ helm delete <release>
```



## error

```
WARNING: Kubernetes configuration file is group-readable. This is insecure. Location: /home/ubuntu/.kube/config
WARNING: Kubernetes configuration file is world-readable. This is insecure. Location: /home/ubuntu/.kube/config
```

## fix by

```
sudo chmod go-r ~/.kube/config
```
