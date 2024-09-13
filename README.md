# taloscon2024
Sources for my Kubevirt on Talos presentation. This repository contains everything for you to get started with KubeVirt on Talos Linux. 

# Directory layout
```
.
├── kubevirt-manifests
│   ├── debian-external-virtualmachine.yaml
│   ├── debian-webserver.yaml
│   ├── fedora-virtualmachine.yaml
│   ├── import-datavolume-debian.yml
│   ├── import-datavolume-fedora40.yml
│   ├── README.md
│   └── server2022-virtualmachine.yaml
├── prerequisites
│   ├── cdi-operator
│   │   ├── cdi-cr.yaml
│   │   └── cdi-operator.yaml
│   ├── kubevirt-manager
│   │   ├── bundled.yaml
│   │   └── README.md
│   ├── kubevirt-operator
│   │   ├── kubevirt-cr.yaml
│   │   └── kubevirt-operator.yaml
│   ├── lmsensors
│   │   ├── daemonset.yaml
│   │   ├── namespace.yaml
│   │   ├── pvc.yaml
│   │   └── webserver.yaml
│   ├── local-path-provisioner
│   │   └── local-path-storage.yaml
│   ├── longhorn
│   │   ├── external-snapshotter
│   │   │   ├── crd
│   │   │   │   ├── groupsnapshot.storage.k8s.io_volumegroupsnapshotclasses.yaml
│   │   │   │   ├── groupsnapshot.storage.k8s.io_volumegroupsnapshotcontents.yaml
│   │   │   │   ├── groupsnapshot.storage.k8s.io_volumegroupsnapshots.yaml
│   │   │   │   ├── kustomization.yaml
│   │   │   │   ├── snapshot.storage.k8s.io_volumesnapshotclasses.yaml
│   │   │   │   ├── snapshot.storage.k8s.io_volumesnapshotcontents.yaml
│   │   │   │   └── snapshot.storage.k8s.io_volumesnapshots.yaml
│   │   │   └── snapshot-controller
│   │   │       ├── kustomization.yaml
│   │   │       ├── rbac-snapshot-controller.yaml
│   │   │       └── setup-snapshot-controller.yaml
│   │   ├── README.md
│   │   ├── storageclass-rwx.yml
│   │   └── volumesnapshotclass-default.yml
│   ├── metallb
│   │   ├── ip-config.yaml
│   │   ├── README.md
│   │   └── values.yml
│   ├── multus
│   │   ├── multus-daemonset-thick.yml
│   │   ├── networkattachmentconfig.yml
│   │   ├── README.md
│   │   ├── whereabouts.cni.cncf.io_ippools.yaml
│   │   ├── whereabouts.cni.cncf.io_overlappingrangeipreservations.yaml
│   │   └── whereabouts-install.yaml
│   └── nfs-subdir-external-provisioner
│       ├── nfs-values-zimaboard.yml
│       └── README.md
├── presentation
│   └── presentation.pdf
└── README.md
```

## kubevirt-manifests

This contains all my yaml files that i used while traveling over the KubeVirt highway. These are KubeVirt for different type of virtual machines. 



## prerequisites

These are all my configurations i used to configure my cluster so KubeVirt works properly in my Homelab:

- multus and whereabouts 
- metallb
- longhorn 
- local path provisioner
- nfs subdir external provisioner
- kubevirt-manager
- cdi and kubevirt operators. 
- lmsensors container
    - A custom made dashboard for lmsensors that i created to monitor the temperatures of my worker nodes. More information can be found [here](https://github.com/MichaelTrip/lmsensors-container). Some configuration is required. please the the README.md in the repository

## presentation

Obviously containing the presentation.pdf of my presentation at TalosCon 2024 😂