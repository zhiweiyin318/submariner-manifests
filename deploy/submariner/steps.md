$ subctl join --kubeconfig /home/centos/kubeconfig-test3 broker-info.subm --clusterid cluster3
* broker-info.subm says broker is at: https://10.0.118.46:42415
* There are 1 labeled nodes in the cluster:
  - test3-worker
    ```
    $ kubectl label node test2-worker submariner.io/gateway=true
    ```
    Discovered network details:
        Network plugin:  generic
        Service CIDRs:   [10.96.0.0/12]
        Cluster CIDRs:   [10.244.0.0/16]
 ✓ Discovering network details
    getNetworkDetails
    getServiceCIDR
    getPodCIDR
 ✓ Validating Globalnet configurations
    
 ✓ Discovering multi cluster details
    AllocateAndUpdateGlobalCIDRConfigMap
 
 ✓ Deploying the Submariner operator
    create crds
        submarinerCrd
        GatewaysCRD
    create ns submariner-operator
    create sa in submariner-operator
    create operator role/rolebinding 
    create cluster role/rolebinding
    UpateSCC
 ✓ Created Lighthouse service accounts and roles
    create role/rolebinding

 ✓ Creating SA for cluster
    create sa for cluster in submariner-k8s-broker
    create rolebinding bind to submariner-k8s-broker-cluster
 ✓ Deploying Submariner
    create ns submariner
    apply submariner_cr
 ✓ Submariner is up and running



1. valid network
   
   update configmap
```
 $ kubectl get configmaps -n submariner-k8s-broker submariner-globalnet-info
```