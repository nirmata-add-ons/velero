# velero
This README documents the `Velero` integration as an add-on that can be deployed on Kubernetes clusters using Nirmata Kubernetes Platform

## what is Velero
`Velero` is a tool that can be used to safely backup and restore, perform disaster recovery, and migrate Kubernetes cluster resources and persistent volumes

## How do I get setup?

1. Clone this repository or add its contents to your own private Git repository.
2. Create a Nirmata catalog application with a Git upstream and select the velero repository with this branch. You can optionally select the kustomization.
3. Edit the catalog application and select an add-on category (e.g. Storage). This is required to select the application as an add-on.
4. Update a Cluster Type, or create a new one, and select the velero add-on application in the "Add-Ons" section. Ensure that the namespace you use is "velero" and environment is "velero -< cluster-name >"
5. Create clusters using the cluster type.
6. If the addon is to be added to a running cluster, create an environment with the namespace "velero" and choose this environment while deploying the application
Verify that the application is running in Nirmata
7. Once the addon is installed, configure velero with the aws access key id and secret access key for the first time. Also setup backup storage location and volume snapshot locations before taking backups. 

## Important:

To use the snapshot functionality of the Amazon EBS CSI driver, you must install the external snapshotter before the installation of the EBS CSI driver. The external snapshotter components must be installed in the following order:
* [CustomResourceDefinition](https://github.com/kubernetes-csi/external-snapshotter/tree/master/client/config/crd) (CRD) for volumesnapshotclasses, volumesnapshots, and volumesnapshotcontents
* [RBAC](https://github.com/kubernetes-csi/external-snapshotter/blob/master/deploy/kubernetes/snapshot-controller/rbac-snapshot-controller.yaml)
* [controller deployment](https://github.com/kubernetes-csi/external-snapshotter/blob/master/deploy/kubernetes/snapshot-controller/setup-snapshot-controller.yaml)
* [VolumeSnapshotClass](https://gist.github.com/nsagark/be1c0a64bc7b2d44080dd9c6af4a53e6)

Before backing and restoring gp3 volumes using `velero`, make sure above compoents are installed in your cluster 
