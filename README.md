# Kubernetes Manifests

Deployment manifests for applications on the LineTen GKE cluster.

## Structure

```
.
├── apps/
│   └── recall-app/
│       ├── base/           # Base manifests
│       └── overlays/dev/   # Dev environment
├── infrastructure/
│   └── atlantis/           # Terraform GitOps
└── README.md
```

## Deploying an App

```bash
kubectl apply -k apps/recall-app/overlays/dev
```

## Adding New Apps

1. Create `apps/<app-name>/base/` with deployment, service, kustomization.yaml
2. Create `apps/<app-name>/overlays/<env>/` with overlay
