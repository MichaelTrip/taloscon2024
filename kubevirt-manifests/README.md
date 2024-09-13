# My Kubevirt manifests

| :exclamation:  These files are only used as a reference and have default usernames and passwords. Please us this as a starting point of creating your own manifests.    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|



This directory contains some KubeVirt manifests i use during my KubeVirt journey.

I will describe these files one by one:

## `debian-external-virtualmachine.yaml`

This is a basic manifest that i use to expose my debian test machine with Multus directly to my Network.

The username of this virtual machine is `kubevirt`, the password is also `kubevirt`.

## `debian-webserver.yaml`

This is a manifest that i use to configure a typical debian webserver. The `cloud-init` configuration is configured as a secret because i am using a base64 string to create a basic php page displaying the hostname. This php page can be found on http://<ipaddress>/hostname.php

The username of this virtual machine is `kubevirt`, the password is also `kubevirt`.

## `fedora-virtualmachine.yaml`

This is a basic fedora virtual machine that basically installs a httpd server and fastfetch. 

The username of this virtual machine is `kubevirt`, the password is also `kubevirt`.

## `import-datavolume-debian.yaml`

This is a DataVolume CR that creates a base disk for Debian 12.

## `import-datavolume-fedora40.yaml`

This is a DataVolume CR that creates a base disk for Fedora 40.

## `server2022-virtualmachine.yaml`

This is a Kubevirt Virtual Machine Manifest that i used to test out server2022 on my KubeVirt cluster.

To make this to work you first have to download a evaluation ISO from Microsoft. After that, you have to upload the iso to Kubevirt by using the `virtctl` command. And before uploading, make sure to to a port-forward to the cdi-proxy to upload the ISO.

1. Create the port-forward to the cdi-proxy:

```bash
$ kubectl port-forward -n cdi svc/cdi-uploadproxy 8443:443
```
2. Open a new terminal and upload the ISO to the Kubevirt cluster:
```bash
$ kubectl virt image-upload pvc win2022-iso --size=6Gi  --access-mode=ReadWriteMany --storage-class=nfs-client-zimaboard --image-path <path-to-your-iso.iso> --uploadproxy-url https://localhost:8443 --insecure
```
3. Apply the manifest.
4. Connect to the VNC console with `kubectl virt console server2022`
5. Install your Windows server 2022.


