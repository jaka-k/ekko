# Namespaces

This directory contains namespace manifests and their applications organized by environment.

## Structure

- `base/` - Base Kustomize configurations for namespaces
- `production/` - Production environment overlays
- `dev/` - Development environment overlays

## Usage

Each namespace should have its base configuration in `base/<namespace-name>/` and environment-specific overlays in `production/<namespace-name>/` and `dev/<namespace-name>/`.

A namespace directory typically contains:
- Namespace definition
- Applications and services within that namespace
- RBAC resources (ServiceAccounts, Roles, RoleBindings)
- ConfigMaps and Secrets
- Network policies

Example structure:
```
namespaces/
├── base/
│   └── my-namespace/
│       ├── kustomization.yaml
│       ├── namespace.yaml
│       ├── my-app/
│       │   ├── deployment.yaml
│       │   └── service.yaml
│       └── rbac.yaml
├── production/
│   └── my-namespace/
│       ├── kustomization.yaml
│       └── patches/
└── dev/
    └── my-namespace/
        ├── kustomization.yaml
        └── patches/
```
