# Kubernetes
## Formation Kubernetes intercontrat

helm create nginx-routing
### Nettoyage des fichiers inutiles
rm -rf nginx-routing/templates/*
rm nginx-routing/templates/.helmignore 2>/dev/null || true

### Linter
helm lint nginx-routing/

### For traefik.containo.us/v1alpha1 - use Traefik v2 CRDs
kubectl apply -f https://raw.githubusercontent.com/traefik/traefik/v2.10/docs/content/reference/dynamic-configuration/kubernetes-crd-definition-v1.yml

### Installation
helm install nginx-routing ./nginx-routing \
  --create-namespace \
  --wait \
  --timeout 120s
