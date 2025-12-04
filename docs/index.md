# csa-demo-container Deployment

## Overview

This repository contains the GitOps deployment configuration for **demo-container** owned by **csa**.

It uses the kubriX SCM generator pattern with Kargo for progressive delivery across environments.

## Repository Structure

```
├── templates/            # Helm templates
│   ├── deployment.yaml
│   ├── service.yaml
│   └── ingress.yaml
├── app-stages.yaml       # Kargo stage definitions
├── values.yaml           # Base Helm values
├── values-dev.yaml       # Dev environment overrides
├── values-test.yaml      # Test environment overrides
├── values-prod.yaml      # Prod environment overrides
└── docs/                 # Documentation (this folder)
```

## Related Repositories

| Repository | Purpose |
|------------|---------|
| [csa-demo-container-dev](https://github.com/mjay-bs-test/csa-demo-container-dev) | Application source code |
| [csa-demo-container-deploy](https://github.com/mjay-bs-test/csa-demo-container-deploy) | GitOps deployment (this repo) |

## Environments

| Environment | URL | Cluster |
|-------------|-----|---------|
| Dev | http://csa-demo-container.dev.tietoevry.platform-engineer.cloud | dev001 |
| Test | http://csa-demo-container.test.tietoevry.platform-engineer.cloud | test001 |
| Prod | http://csa-demo-container.prod.tietoevry.platform-engineer.cloud | prod001 |

## Deployment Pipeline

1. **Dev**: Auto-deployed on new container image
2. **Test**: Promoted via Kargo after dev validation
3. **Prod**: Promoted via Kargo after test validation

## Links

- [ArgoCD Application](https://argocd.tietoevry.platform-engineer.cloud/applications/adn-csa/csa-demo-container)
- [Kargo Project](https://kargo.tietoevry.platform-engineer.cloud/project/csa-demo-container-kargo-project)
- [Grafana Dashboard](https://grafana.tietoevry.platform-engineer.cloud/d/k8s_views_ns/kubernetes-views-namespaces)

## Support

For issues or questions, contact the **csa** team.
