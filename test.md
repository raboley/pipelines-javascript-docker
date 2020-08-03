# Running this env deploy test

## Setup infra

```bash
RESOURCE_GROUP=rab-env-test-rg
CONTAINER_REGISTRY=rabenvcr
# Create a resource group
az group create --name $RESOURCE_GROUP --location eastus

# Create a container registry
az acr create --resource-group $RESOURCE_GROUP --name $CONTAINER_REGISTRY --sku Basic

# Create a Kubernetes cluster 
az aks create \
    --resource-group $RESOURCE_GROUP \
    --name myapp \
    --node-count 1 \
    --enable-addons monitoring \
    --generate-ssh-keys \
    --kubernetes-version 1.16.10

```