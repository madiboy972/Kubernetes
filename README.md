# Kubernetes
# Formation Kubernetes intercontrat

helm create nginx-routing
# Nettoyage des fichiers inutiles
rm -rf nginx-routing/templates/*
rm nginx-routing/templates/.helmignore 2>/dev/null || true

# Linter
helm lint nginx-routing/

# Installation
helm install nginx-routing ./nginx-routing \
  --create-namespace \
  --wait \
  --timeout 120s
