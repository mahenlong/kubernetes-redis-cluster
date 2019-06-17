# Kubernetes Redis-5.0.4 Cluster


### [Build Docker image](README-build-docker.md)


### Create NFS storages


### Create Persistent Volumes

```
kubectl create -f persistentvolume
```

### Create Persistent Volumes Claims

```
kubectl create -f persistentvolumeclaims
```

### Create Redis Cluster Configuration

```
kubectl create -f deployment-configmaps
```

### Create Redis Services

```
kubectl create -f deployment-services
```

### Create Redis Nodes

```
kubectl create -f deployment
```

### Connect Nodes


```
redis-cli --cluster create  --cluster-replicas 1 \
  10.10.100.11:6379 \
  10.10.100.12:6379 \
  10.10.100.13:6379 \
  10.10.100.14:6379 \
  10.10.100.15:6379 \
  10.10.100.16:6379
```

### Accessing redis cli

Connect to any redis pod
```
kubectl exec -it <podName> -- /bin/bash
```
Access cli
```
/usr/local/bin/redis-cli -c -p 6379
```
To check cluster nodes
```
/usr/local/bin/redis-cli -p 6379 cluster nodes
```


### Contribs

```
Originally contributed by Kelsey Hightower (https://github.com/kelseyhightower/kubernetes-redis-cluster)
Special thanks to following forks
https://github.com/matiasinsaurralde/kubernetes-redis-cluster
https://github.com/cwza/kubernetes-redis-cluster
```
