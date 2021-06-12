# Multiplayer Crossword K8s Setup
## Deployment
* Create secret for Docker registry
   ```bash
    kubectl create secret generic regcred \
    --from-file=.dockerconfigjson=$HOME/.docker/config.json \
    --type=kubernetes.io/dockerconfigjson
    ```
* Create deployments and services
   ```bash
   kubectl create -f frontend-service.yaml,frontend-deployment.yaml,backend-deployment.yaml,backend-service.yaml
   ```
* Ensure static IP matches that set in the domain.
