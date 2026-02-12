# Ekko - GitOps Repository

This repository contains Kubernetes manifests managed by Flux for personal applications.

## Structure

```
├── namespaces/         # Namespace manifests and applications
│   ├── base/          # Base configurations
│   ├── production/    # Production overlays
│   └── dev/           # Development overlays
├── infrastructure/     # Infrastructure components
│   ├── base/          # Base configurations
│   ├── production/    # Production overlays
│   └── dev/           # Development overlays
└── clusters/          # Flux cluster configs
    ├── production/    # Production cluster
    └── dev/           # Development cluster
```

## Getting Started

1. **Bootstrap Flux** on your cluster:
   ```bash
   flux bootstrap git \
     --url=<repository-url> \
     --branch=master \
     --path=clusters/production  # or clusters/dev
   ```

2. **Add infrastructure** components in `infrastructure/base/`

3. **Add namespaces and applications** in `namespaces/base/`

4. **Create environment overlays** in `production/` or `dev/` directories

## Workflow

- All changes are made via Git commits
- Flux automatically syncs changes to the cluster
- Use Kustomize for environment-specific configurations
- Organize applications by namespace for better isolation and management

## Documentation

- [Flux Documentation](https://fluxcd.io/docs/)
- [Kustomize Documentation](https://kubectl.docs.kubernetes.io/references/kustomize/)
