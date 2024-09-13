# taloscon2024
Sources for my Kubevirt on Talos presentation



# Directory layout




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

