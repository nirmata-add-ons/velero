# velero
This README documents the velero integration as an add-on that can be deployed on Kubernetes clusters using Nirmata Kubernetes Platform

## what is Velero
Velero is a tool to safely backup and restore, perform disaster recovery, and migrate Kubernetes cluster resources and persistent volumes

## How do I get setup?

Clone this repository or add its contents to your own private Git repository.
Create a Nirmata catalog application with a Git upstream and select the cert-manager repository. You can optionally select the kustomization.
Edit the catalog application and select an add-on category (e.g. Security). This is required to select the application as an add-on.
Update a Cluster Type, or create a new one, and select the cert-manager add-on application in the "Add-Ons" section. Ensure that the namespace you use is "cert-manager" and environment is "cert-manager -< cluster-name >"
Create clusters using the cluster type.
If the addon is to be added to a running cluster, create an environment with the namespace "cert-manager" and choose this environment while deploying the application
Verify that the application is running in Nirmata
