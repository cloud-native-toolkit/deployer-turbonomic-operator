# Techzone Deployer Turbonomic Operator pipelines

This repository contains a set of Tekton pipelines to deploy the Turbonomic Operator in an IBM Technology Zone `deployer` cluster.

## Prerequisites

An IBM Technology Zone `deployer` cluster is assumed to be configured with an appropriate Red Hat OpenShift version for the solution you wish to deploy, with appropriate sizing.

A `deployer` cluster is configured with the following items:

- ExternalSecrets operator deployed with a ClusterSecretStore configured. The remote ExternalSecrets secret store must include an IBM Entitlement Key.
- Techzone Deployer Tekton tasks deployed ([deploy YAML](https://github.com/cloud-native-toolkit/deployer-tekton-tasks/blob/main/argocd.yaml)).
- OpenShift GitOps configured with [One Touch Provisioning ArgoCD instance](https://github.com/one-touch-provisioning/otp-gitops), and any relevant RBAC rules.
- OpenShift Pipelines operator deployed.
- OpenShift Data Foundation

## Repository organisation

The top-level folders in this repository are for the different Turbonomic Operator versions. In each top-level folder there will be a pipeline and a pipelinerun.

```
.
└── turbonomic-version/
    ├── pipeline.yaml
    └── pipelinerun.yaml
```

## Deployment Scripts

`oc apply -f turbonomic-operator-pipeline.yaml` to install configure service account and install tasks and pipeline

`oc create -f turbonomic-operator-pipeline-run.yaml` to kick off pipeline with default Turbonomic version 8.9.5
