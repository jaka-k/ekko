# Infrastructure

This directory contains infrastructure component manifests (controllers, operators, etc.) organized by environment.

## Structure

- `base/` - Base Kustomize configurations for infrastructure components
- `production/` - Production environment overlays
- `dev/` - Development environment overlays

## Components

Infrastructure typically includes:
- Ingress controllers
- Cert managers
- Monitoring stack (Prometheus, Grafana)
- Logging stack
- Service meshes
- Storage providers
- Other cluster-wide services

## Usage

Each infrastructure component should have its base configuration in `base/<component>/` and environment-specific overlays in `production/<component>/` and `dev/<component>/`.
