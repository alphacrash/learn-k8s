# Learn Kubernetes (k8s)

Udemy - https://www.udemy.com/course/kubernetes-training-learn-kubernetes-from-zero-to-cloud/

This repo contains code made while learning the course.

## Logs

```bash
kubectl logs -f grade-submission-api-65756568d7-lbtcs -n grade-submission
```

## Delete Command

```bash
kubectl delete deployments --all -n grade-submission
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