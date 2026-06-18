# Kubernetes ConfigMap and Secret
This repository demonstrates how to manage application configuration and sensitive data in Kubernetes using ConfigMaps and Secrets.  

The project deploys an Eclipse Mosquitto and mounts both a ConfigMap and a Secret as files inside the container. This approach follows Kubernetes best practices by separating configuration and credentials from the container image.

## Deploying the Project
```python
kubectl apply -f config-file.yaml
kubectl get configMap
```

## Create Secret
```python
kubectl apply -f secret-file.yaml
kubectl get secret
```

## Deploy Mosquitto
```python
kubectl apply -f mosquitto.yaml
kubectl get pods
```

## Inspect Mounted Files
### Access the running pod:
```python
kubectl exec -it <pod-name> -- /bin/sh
```

### View configuration files:
```python
ls -l /mosquitto/config
```

### View secret files:
```python
ls -l /mosquitto/secret
```

## Verify Deployment
### Describe the deployment:
```python
kubectl describe deployment mosquitto
```

### Check mounted volumes:
```python
kubectl describe pod <pod-name>
```
