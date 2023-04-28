# deployer-turbonomic-operator

Tektoncd pipeline to deploy the Turbonomic Operator for IBM TechZone Deployer (experimental)

## Prerequisites

- Openshift Cluster with OpenShift Pipelines 1.8 installed

## Tasks

Currently uses oc client from tekton hub

## Usage

###

oc apply -f tekton.yaml to install configure service account and install tasks and pipeline
oc create -f install-turbo-pipeline-run.yaml to kick off pipeline
