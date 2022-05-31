# SC01-TC01: create new Cluster via TMC and install/manage packages.

## Test Case Summary

The test case procedure demonstrates enabling a compatible vSphere 7 cluster as a SC. After enabling the SC, the procedure verifies that the SC Web UI is available for downloading client tools and the API processes authentication, authorization,  and Kubernetes resource requests.

1) create new cluster
---
<img width="1455" alt="image" src="https://user-images.githubusercontent.com/22165556/171159789-ee6b9991-9f88-4fe6-bdde-854535ca105d.png">


2) make sure respository is accesable from TMC 

<img width="1530" alt="image" src="https://user-images.githubusercontent.com/22165556/171160041-a5ea094b-635a-42ea-9224-bad9e70e2a00.png">

3) install Cert Manager package from the catalog tab: 

<img width="1518" alt="image" src="https://user-images.githubusercontent.com/22165556/171160215-ab53f352-c167-49f6-b052-06c6aab8ae5e.png">

4) from the addons/installed confirm that the package status is "Succeeded"

<img width="1538" alt="image" src="https://user-images.githubusercontent.com/22165556/171160313-af7649c5-f0f6-4bd3-9bd6-c0447677bcba.png">


---

## Prerequisites

* vSphere Administrator console and user credentials
* [Licensing for vSphere with Kubernetes](https://docs.vmware.com/en/VMware-vSphere/7.0/vmware-vsphere-with-kubernetes/GUID-9A190942-BDB1-4A19-BA09-728820A716F2.html) ; vSAN Advanced only required if using vSAN
* [vSphere with Kubernetes System Requirements and Topologies](https://docs.vmware.com/en/VMware-vSphere/7.0/vmware-vsphere-with-kubernetes/GUID-B1388E77-2EEC-41E2-8681-5AE549D50C77.html)
* [Create Storage Policies for vSphere with Kubernetes](https://docs.vmware.com/en/VMware-vSphere/7.0/vmware-vsphere-with-kubernetes/GUID-544286A2-A403-4CA5-9C73-8EFF261545E7.html)
* [Configure vSphere with Kubernetes to Use NSX-T Data Center](https://docs.vmware.com/en/VMware-vSphere/7.0/vmware-vsphere-with-kubernetes/GUID-8D0E905F-9ABB-4CFB-A206-C027F847FAAC.html)
