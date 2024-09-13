# Howto install Longhorn?

```bash
$ helm repo add longhorn https://charts.longhorn.io
$ helm repo update
$ helm install longhorn longhorn/longhorn --namespace longhorn-system --create-namespace --version 1.6.1
```

# Storageclass

The file `storageclass-rwx.yml` contains the `storageclass` that is used to configure `ReadWriteMany` for Longhorn.

# VolumeSnapshotClass

The file `volumesnapshotclass-default.yml` contains a basic configurion of a `VolumeSnapshotClass` which can be used to create snapshots of your virtual machines.

# external-snapshotter directory

This directory contains manifests to deploy a external-snapshotter. This is the basic external-snapshotter that coms from the Kubernetes SIG storage group. This is a prerequiste for Snapshots and KubeVirt to work properly
