# MetalLB


## howto install
```bash
$ helm install metallb metallb/metallb -f values.yml --namespace kube-system
```


## Why do i use MetalLB ?

I use MetalLB to configure a Service of type `LoadBalancer` which i then use to expose my virtual machines to the network. This is another way if you don´t want to use Multus.

