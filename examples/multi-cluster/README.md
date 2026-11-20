# Multi-Cluster

This example demonstrates a two-cluster Stellar deployment with an active-primary validator in one cluster and a standby validator in the other, while Horizon and Soroban RPC can serve traffic actively in both regions. It also shows cross-cluster DNS failover, secure peer communication, and local multi-cluster setup with kind.

## Files and folders

- [`active-active.yaml`](active-active.yaml) — Placeholder namespace manifest for the active-active multi-cluster namespace.
- [`active-passive.yaml`](active-passive.yaml) — Placeholder namespace manifest for the active-passive topology.
- [`argocd-application.yaml`](argocd-application.yaml) — Placeholder namespace manifest for an Argo CD application deployment.
- [`cluster-a/`](cluster-a/) — Resources for primary Cluster A, including the voting validator, active Horizon and Soroban nodes, ingress, and ExternalDNS.
- [`cluster-b/`](cluster-b/) — Resources for secondary Cluster B, including a synced standby validator, active RPC nodes, ingress, and ExternalDNS.
- [`external-dns-failover.yaml`](external-dns-failover.yaml) — Placeholder namespace manifest for configuring ExternalDNS-based failover.
- [`kind/`](kind/) — kind cluster configurations and a bridge-network script for creating and provisioning both local clusters.
- [`kustomization.yaml`](kustomization.yaml) — Kustomize configuration that assembles the demo namespace, workloads, services, DNS, network policy, and image settings.
- [`mtls/`](mtls/) — Shared-CA, peer-certificate, and Istio peer-authentication manifests for mutual TLS between clusters.
- [`network-policy.yaml`](network-policy.yaml) — Placeholder namespace manifest for cross-cluster network isolation rules.
