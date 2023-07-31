# lern-helm
lerning helm

## install 

```

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
