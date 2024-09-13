# nfs subdir external provisioner

## Howto install
```bash
$ helm repo add nfs-subdir-external-provisioner https://kubernetes-sigs.github.io/nfs-subdir-external-provisioner/
$ helm install nfs-subdir-external-provisioner nfs-subdir-external-provisioner/nfs-subdir-external-provisioner -f nfs-values.yml
```

## Why i use this?

I use this mainly because the nfs csi provisioner had some kind of bug that made it impossible to run on Talos. the nfs subdir external provisioner is also a way to store things on NFS. 