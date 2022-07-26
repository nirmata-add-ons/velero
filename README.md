# velero
This README documents the velero integration as an add-on that can be deployed on Kubernetes clusters using Nirmata Kubernetes Platform

## what is Velero
Velero is a tool to safely backup and restore, perform disaster recovery, and migrate Kubernetes cluster resources and persistent volumes

## How do I get setup?

1. Clone this repository or add its contents to your own private Git repository.
2. Create a Nirmata catalog application with a Git upstream and select the velero repository with this branch. You can optionally select the kustomization.
3. Edit the catalog application and select an add-on category (e.g. Storage). This is required to select the application as an add-on.
4. Update a Cluster Type, or create a new one, and select the velero add-on application in the "Add-Ons" section. Ensure that the namespace you use is "velero" and environment is "velero -< cluster-name >"
5. Create clusters using the cluster type.
6. If the addon is to be added to a running cluster, create an environment with the namespace "velero" and choose this environment while deploying the application
Verify that the application is running in Nirmata
7. Once the addon is installed, configure velero with the aws access key id and secret access key for the first time. Also setup backup storage location and volume snapshot locations before taking backups. 
