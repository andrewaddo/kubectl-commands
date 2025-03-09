# kubectl-commands
Common kubectl commands

```
kubectl get --help
kubectl get no
kubectl get po
kubectl describe pod $POD_NAME
kubectl get events
-- deployment variable
DEPLOYMENT_NAME=vllm-h100-llama370b-deployment
kubectl describe deployment/$DEPLOYMENT_NAME
kubectl logs deployment/$DEPLOYMENT_NAME
kubectl logs -f deployment/$DEPLOYMENT_NAME -n default
-- app variable
APP_NAME=model-server
kubectl logs -f -l app=$APP_NAME
kubectl wait --for=condition=Available --timeout=700s deployment/$DEPLOYMENT_NAME

```


Common gcloud commands

```
gcloud config set container/cluster $CLUSTER_NAME
gcloud container node-pools list

-- connect kubectl with the API server
gcloud container clusters get-credentials $CLUSTER_NAME --location=us-central1

-- check GPU assignment for nodes
kubectl get nodes -o json | jq -r '.items[] | {name:.metadata.name, gpus:.status.capacity."nvidia.com/gpu"}'
```
