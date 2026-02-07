# Learn Kubernetes (k8s)

Udemy - https://www.udemy.com/course/kubernetes-training-learn-kubernetes-from-zero-to-cloud/

This repo contains code made while learning the course.

## Get

```bash
kubectl get services -n grade-submission
```

## Logs

```bash
kubectl logs -f grade-submission-api-65756568d7-lbtcs -n grade-submission
```

## Delete Command

```bash
kubectl delete deployments --all -n grade-submission
kubectl delete deployments,statefulsets,pvc,pod,hpa,services,secret,configmap --all -n grade-submission
```

## Rollback

```bash
kubectl rollout undo deployment/grade-submission-api -n grade-submission
```

## Cleanup

1. Clean Helm Repos and Docker Images

```bash
# Remove helm repos
helm repo list
helm repo remove <repo_name>
# Remove docker images
docker images
docker system prune -a
```

2. Open Docker Desktop
    * Disable Kubernetes
    * Delete all containers, images and builds

## Metrics Server

```bash
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml && kubectl patch deployment metrics-server -n kube-system --type='json' -p='[{"op": "add", "path": "/spec/template/spec/containers/0/args/-", "value":"--kubelet-insecure-tls"}]'
```

Check cpu and memory usage
```bash
kubectl top pods -n grade-submission
```

## Nginx

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.8.2/deploy/static/provider/cloud/deploy.yaml
```

## Helm commands

```bash
helm template .
helm package .
helm install <name> <package_name>
helm list .
helm uninstall <package_name>
```