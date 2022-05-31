# VMware vSphere 7 with Kubernetes

## Proof of Concept (PoC) Test Plan

> ***The [sharing guide](Sharing.md) guide is required reading for anyone who intends to use the assets in this repository***
> ***The assets in this repository `CANNOT` be shared with customers in any other way***


## About this Guide

[vSphere 7 with Kubernetes](https://www.vmware.com/products/vsphere/projectpacific.html) empowers IT, operators and developers, to accelerate innovation by converging containers and virtual machines (VM) into VMware’s vSphere server virtualization platform with native Kubernetes. VMware has leveraged Kubernetes to rearchitect vSphere and extend its capabilities to all modern and traditional applications.  The vSphere 7 with Kubernetes PoC Test Plan details the approach and procedures for testing a vSphere 7 with Kubernetes PoC and evaluating the results in comparison with the Customer’s success criteria.

## Intended Audience

This guide is for cloud architects, engineers, administrators, and developers whose organization has an interest in integrating and evaluating vSphere 7 with Kubernetes with their VMware vSphere cloud infrastructure and management utilities.

## vSphere 7 with Kubernetes PoC Test & Evaluation Overview

### Scope

The vSphere 7 with Kubernetes PoC test and evaluation process focuses on demonstrating functional operation, capabilities, and features of the vSphere 7 with Kubernetes platform and Tanzu Kubernetes Clusters (TKC) in a developmental environment.

**IMPORTANT** - This pre-sales offering does not consider all best practices and recommendations for production or extended pilot use.  VMware strongly encourages Customers to thoroughly review all publicly available product documentation and engage with the Professional Services Organization and Partners before going forward with any production design decisions. The PoC evaluation system is not the appropriate platform for intensive and lengthy performance testing and evaluation.

### Goals and Objectives

The goal is promoting Customer confidence in the vSphere 7 with Kubernetes product through an inclusive test approach and procedures worthy for judging the platform’s operational effectiveness and suitability. The following table lists the vSphere 7 with Kubernetes PoC test process' objectives:

ID | Objective |
:-- | :-- |
OB01|Prove the automation and simplicity of deploying and operationalizing Kubernetes clusters
OB02|Reveal the advanced, on-demand networking and security capabilities that vSphere 7 with Kubernetes and NSX-T enable through the Kubernetes Container Network Interface (CNI) plug-in
OB03|Validate the support for stateful applications and the multitude of storage options that vSphere 7 with Kubernetes enables through the vSphere Cloud Native Storage (CNS) – Container Storage Interface (CSI)
OB04|Show the level of monitoring, alerting, and visibility available through integrations with VMware vRealize and Wavefront products and other Open Source Software (OSS) alternatives
OB05|Exhibit the availability of multi-master clusters and the self-healing resiliency of the individual cluster nodes
OB06|Demonstrate the ability for operators to easily and quickly scale-out Kubernetes clusters resources on-demand
OB07|Without disruption to running containerized applications, demonstrate patching and upgrading Kubernetes clusters
OB08|Validate containerized application portability, interoperability, and consistency between Kubernetes tools and environments
OB09|Demonstrate integration of vSphere 7 with Kubernetes and development pipeline automation tools
OB10|Show the coexistence of both traditional VM-based and containerized applications running parallel on common infrastructure resources
OB11|Demonstrate vSphere 7 with Kubernetes multi-tenancy and Role Based Access Control (RBAC) capabilities for enterprise environments
OB12|Demonstrate managing and securely serving images for containerized applications

## vSphere 7 with Kubernetes PoC Test Approach

The approach centers on scenarios that stimulate and exercise numerous aspects of the system in parallel. Because of the many interactions with scenarios, the potential for uncovering design deficiencies increases. Ultimately, identifying the deficiencies and sources of the deficiencies so that Customers’ have a sound basis for their decision to move forward with vSphere 7 with Kubernetes is the design of the approach.

### Process Flow

The quality and completeness of the Customer test goals and objectives, or success criteria, are the key input to constructing useful test cases and producing meaningful results. With that input, the Customer Technical Leads and VMware Systems Engineers can derive a base set of requirements. Then, after analyzing the requirements, generate test scenarios that represent the operational use of the system.  Next, develop test cases within each scenario, ensuring complete allocation of requirements and quantifiable expectations. Finally, execute the test cases to validate system operation and verify compliance with the requirements. The image below illustrates the general flow of the test development and execution process for the vSphere 7 with Kubernetes PoC

![Test Plan Process](images/TestPlanProcessFlow.png)

### Summary Requirements Analysis

The following table contains an assemblage of requirements inferred by the technology; revised and repurposed from Customer's RFIs; derived from frequently mentioned Customers' goals and objectives; community involvement; and learned through research and development. The requirements form the basis of the test cases inventory and the test procedures, detailed in later sections. Each requirement maps to its overarching objective and test case(s) responsible for demonstrating functional compliance. Because the test approach is scenario-driven, there is not a 1:1 relationship for all requirements and some requirements may be indirectly satisfied by an encompassing test case.

   ID  | Requirements Description | OBJ | Test Case ID(s)|
--- | --- | --- |--- |
RQ01–01| vSphere 7 with Kubernetes shall support deploying Kubernetes clusters within at least one (1) release of the current GKE GA release | OB01 | [SC01-TC01](sc01/sc01-tc01.md), [SC01-TC04](sc01/sc01-tc04.md), [SC06-TC01](sc06/sc06-tc01.md), [SC06-TC02](sc06/sc06-tc02.md) |
RQ01–02| vSphere 7 with Kubernetes shall deliver a single platform API for deploying multiple Kubernetes clusters | OB01 | [SC01-TC04](sc01/sc01-tc04.md), [SC06-TC02](sc06/sc06-tc02.md) |
RQ01–03| vSphere 7 with Kubernetes shall enable deploying a Kubernetes cluster with a single, one (1) line command | OB01 | [SC01-TC04](sc01/sc01-tc04.md), [SC06-TC02](sc06/sc06-tc02.md) |
RQ01–04| vSphere 7 with Kubernetes shall deliver the ability to customize templates for deploying Kubernetes cluster of variable sizes. | OB01 | [SC01-TC04](sc01/sc01-tc04.md), [SC06-TC02](sc06/sc06-tc02.md) |
RQ01–05| vSphere 7 with Kubernetes shall enable deleting a Kubernetes cluster and release resources back to the platform with a single, one (1) line. | OB01 | [SC04-TC07](sc04/sc04-tc07.md), [SC06-TC01](sc06/sc06-tc01.md) |
RQ02–01| vSphere 7 with Kubernetes shall facilitate the automatic provisioning of Layer-7 HTTP load-balancers for Kubernetes ingress resources. | OB02 | [SC02-TC01](sc02/sc02-tc01.md), [SC02-TC03](sc02/sc02-tc03.md), [SC02-TC05](sc02/sc02-tc05.md) |
RQ02–02| vSphere 7 with Kubernetes shall facilitate the automatic provisioning of Layer-7 HTTPS load-balancers, with SSL/TLS pass-through and SSL/TLS-termination for Kubernetes ingress resources | OB02 | [SC02-TC04](sc02/sc02-tc04.md), [SC02-TC06](sc02/sc02-tc06.md) |
RQ02–03| vSphere 7 with Kubernetes shall allow the importation of custom CA-signed certificates for use with Kubernetes ingress resources | OB02 | [SC02-TC04](sc02/sc02-tc04.md), [SC02-TC06](sc02/sc02-tc06.md) |
RQ02–04| vSphere 7 with Kubernetes shall enable the ability for a Kubernetes service to automatically provision a Layer 4 TCP/UDP load-balancer | OB02 | [SC02-TC02](sc02/sc02-tc02.md), [SC01-TC07](sc01/sc01-tc07.md), [SC02-TC03](sc02/sc02-tc03.md), [SC02-TC04](sc02/sc02-tc04.md), [SC02-TC05](sc02/sc02-tc05.md), [SC02-TC06](sc02/sc02-tc06.md), [SC02-TC07](sc02/sc02-tc07.md),  [SC02-TC10](sc02/sc02-tc10.md), [SC02-TC11](sc02/sc02-tc11.md), [SC03-TC05](sc03/sc03-tc05.md), [SC04-TC05](sc04/sc04-tc05.md), [SC06-TC03](sc06/sc06-tc03.md) |
RQ02–05| vSphere 7 with Kubernetes shall leverage SDN to automate applying the required network topology for supporting isolated Kubernetes clusters and namespaces | OB02 | All test cases that include either deploying a Kubernetes cluster(s) or creating a Kubernetes namespace(s) |
RQ02–06| vSphere 7 with Kubernetes shall automate the network routing, allowing for Kubernetes clusters and deployed containerized applications to communicate within the cluster and with the corporate infrastructure | OB02 | All test cases that include either deploying a Kubernetes cluster or creating a Kubernetes namespace(s) and containerized application(s) |
RQ02–07| vSphere 7 with Kubernetes shall support on-demand configuration of network security policies, which allow for micro-segmenting flows between two (2) or more pods sharing a common network or between namespaces and external IP networks. | OB02 | [SC02-TC08](sc02/sc02-tc08.md), [SC02-TC09](sc02/sc02-tc09.md) |
RQ02–08| vSphere 7 with Kubernetes shall support layering service mesh technologies on TKC for application traffic management, security, and observability  | OB02 | [SC02-TC07](sc02/sc02-tc07.md) |
RQ03–01| vSphere 7 with Kubernetes shall automate the Kubernetes storage provider integration so Kubernetes pods can mount static and dynamic persistent volumes from existing, shared NFS, iSCSI, vSAN, or Fibre Channel datastores | OB03 | [SC02-TC11](sc02/sc02-tc11.md), [SC02-TC10](sc02/sc02-tc10.md), [SC03-TC05](sc03/sc03-tc05.md), [SC04-TC05](sc04/sc04-tc05.md), [SC06-TC02](sc06/sc06-tc02.md), [SC06-TC03](sc06/sc06-tc03.md) |
RQ04–01| vSphere 7 with Kubernetes shall generate and send syslog messages to a collection server for platform control plane events | OB04 | [SC03-TC03](sc03/sc03-tc03.md) |
RQ04–02| vSphere 7 with Kubernetes shall enable DevOps Engineers and Application Developers with the ability to create custom logging policies for directing cluster and pod-level event messages to a specific collection server | OB04 | [SC03-TC03](sc03/sc03-tc03.md) |
RQ04–03| vSphere 7 with Kubernetes shall integrate with vRealize Operations for visibility into a Kubernetes cluster(s) topology, monitoring key metrics, generating alerts for monitored objects, and tracing issues between integrated system components | OB04 | [SC03-TC02](sc03/sc03-tc02.md) |
RQ04–04| vSphere 7 with Kubernetes shall integrate with the Wavefront SaaS for metrics collection and reporting, and extremely fine visibility into a Kubernetes cluster(s), cluster components’ resources, and the performance of containerized applications | OB04 | [SC03-TC04](sc03/sc03-tc04.md) |
RQ04–05| vSphere 7 with Kubernetes shall support the deployment and integration of the OSS application, Prometheus, to Kubernetes clusters for metric monitoring and alerting | OB04 | [SC03-TC05](sc03/sc03-tc05.md) |
RQ04–06| vSphere 7 with Kubernetes shall allow Kubernetes cluster users to collect information using the standard kubectl CLI. | OB04 | [SC01-TC01](sc01/sc01-tc01.md), [SC01-TC04](sc01/sc01-tc04.md), and all test cases that involve a user interacting with a SC or TKC via CLI tools. |
RQ04–07| vSphere 7 with Kubernetes shall enable Kubernetes cluster administration using the standard Kubernetes Dashboard web UI | OB04 | [SC01-TC07](sc01/sc01-tc07.md) |
RQ04–08| vSphere 7 with Kubernetes shall support registration of TKC(s) with Tanzu Mission Control (TMC) for global visibility, scalable operations, and consistent policy management | OB04 | [SC03-TC06](sc03/sc03-tc06.md) |
RQ05–01| vSphere 7 with Kubernetes shall enable the ability to deploy highly-available Kubernetes clusters with a minimum of three (3) master nodes | OB05 | [SC01-TC01](sc01/sc01-tc01.md), [SC01-TC04](sc01/sc01-tc04.md) |
RQ05–02| vSphere 7 with Kubernetes shall automatically detect a faulty Kubernetes node and automate the node recovery process to restore the prescribed Kubernetes cluster configuration | OB05 | [SC04-TC01](sc04/sc04-tc01.md), [SC04-TC02](sc04/sc04-tc02.md) |
RQ06–01| vSphere 7 with Kubernetes shall facilitate requests to scale-out Kubernetes clusters by orchestrating the incremental addition or deletion of a cluster’s workers nodes | OB06 | [SC04-TC03](sc04/sc04-tc03.md) |
RQ07–01| vSphere 7 with Kubernetes shall automate release upgrades to Kubernetes clusters without impacting the availability of deployed applications during the process | OB07 | [SC04-TC06](sc04/sc04-tc06.md) |
RQ07–02| vSphere 7 with Kubernetes shall provide the ability for platform administrators to backup and restore the vSphere 7 with Kubernetes control plane | OB07 | [SC04-TC05](sc04/sc04-tc05.md) |
RQ08–01| vSphere 7 with Kubernetes support the deployment of curated, containerized application using the Helm package manager | OB08 | [SC05-TC04](sc05/sc05-tc04.md), [SC03-TC05](sc03/sc03-tc05.md), [SC06-TC02](sc06/sc06-tc02.md) |
RQ08–02| vSphere 7 with Kubernetes shall support the portability and compatibility of containerized application specifications between Kubernetes environments | OB08 | All test cases that deploy a sample application(s) and use publicly available specifications. See the test cases’ test data attribute for public references |
RQ09–01| vSphere 7 with Kubernetes shall support the integration with CI/CD automation tools | OB09 | [SC06-TC01](sc06/sc06-tc01.md), [SC06-TC02](sc06/sc06-tc02.md), [SC06-TC03](sc06/sc06-tc03.md), [SC06-TC04](sc06/sc06-tc04.md) |
RQ10–01| vSphere 7 with Kubernetes shall support deploying Kubernetes clusters and respective containerized applications alongside traditional virtual machines, which share common infrastructure resources | OB10 | [SC02-TC10](sc02/sc02-tc10.md) |
RQ10–02| vSphere 7 with Kubernetes shall support multi-tiered applications in which containerized applications require interaction with traditional VM-based workloads | OB10 | [SC02-TC10](sc02/sc02-tc10.md) |
RQ11–01| vSphere 7 with Kubernetes shall provide the ability to authenticate users' API requests through external corporate LDAP services | OB11 | [SC01-TC01](sc01/sc01-tc01.md), [SC01-TC02](sc01/sc01-tc02.md), [SC01-TC05](sc01/sc01-tc05.md) |
RQ12–01| vSphere 7 with Kubernetes shall include a private registry that supports multi-tenancy and RBAC policies for container image repositories | OB12 | [SC05-TC01](sc05/sc05-tc01.md) |
RQ12–02| vSphere 7 with Kubernetes shall deliver a private registry that automatically scans stored container images for known vulnerabilities and analyses threat severity levels | OB12 | [SC05-TC02](sc05/sc05-tc02.md)|
RQ12–03| vSphere 7 with Kubernetes shall provide a private registry that ensures image authenticity and enforces policies to prevent deploying untrusted images | OB12 | [SC05-TC03](sc05/sc05-tc03.md) |
RQ12–04| vSphere 7 with Kubernetes shall support the integration with public and other private container registries | OB12 | By default, all test cases deploy container images, pull from public repository |
RQ12–05| vSphere 7 with Kubernetes shall support the ability to deploy and manage applications on TKC from a web-based catalog UI  | OB12 | [SC05-TC05](sc05/sc05-tc05.md) |

## vSphere 7 with Kubernetes PoC Test System Users and Roles

>NOTE: BEFORE PROCEEDING TO THE TEST CASES, READ THIS SECTION IN ITS ENTIRETY AS IT INCLUDES PREPARATIONS AND PREREQUISITES REQUIRED TO SUCCESSFULLY RUN THE TEST CASES.

The test approach bases the test scenarios and executing the test procedures from the perspective of standard operations and developments roles. System user accounts or groups of users map to symbolizing roles defined within the vSphere 7 with Kubernetes platform and Kubernetes clusters. Following user authentication, a user’s role association determines his/her level of authorization and entitlements while interacting with the interfaces and system resources.

vSphere 7 with Kubernetes integrates with vCenter Single Sign-On (SSO), which is an authentication broker and security token exchange infrastructure, for authenticating system users and authorizing access to system resources. vCenter SSO supports multiple identity sources including local domain, Active Directory, and LDAP. Securing access control for vSphere 7 with Kubernetes requires applying privilege policies at multiple layers in the stack. Executing this test plan requires establishing user accounts and groups in the vCenter SSO local domain and/or linked identity source(s). The following image provides a conceptual representation of how the test plan organizes users and groups membership. Additional information on configuring [Identify Sources for vCenter Server with vCenter Single Sign-On is available on VMware Docs](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vsphere.authentication.doc/GUID-1F0106C9-0524-4583-9AC5-A748FD1DC4C5.html).
![Groups and Users](images/TestPlanGroupsUsers.png)

### vSphere Administrator

As a vSphere administrator, the primary interface for interacting with the vSphere with Kubernetes platform is the vSphere Client. At a high level, vSphere Administrators’ responsibilities involve configuring a Supervisor Cluster and namespaces, where DevOps engineers can deploy Kubernetes workloads. vSphere Administrators should have excellent knowledge about the vSphere and NSX-T technologies, and basic understanding about Kubernetes.

Test cases involving the vSphere administrator role require at least one (1) user account that is either a member of the vCenter SSO, Administrators group or mapped to a vCenter role with the following privileges and permissions for the participating vSphere cluster(s).

* **Namespaces.Modify cluster-wide configuration** or **Namespaces.Modify namespace configuration**
* **Profile-driven storage. Profile-driven storage view** and **update**
* **vSphere Tagging.Create vSphere Tag** on the root vCenter Server instance
* **vSphere Tagging.Create vSphere Tag** Category on the root vCenter Server instance
* **vSphere Tagging.Assign** and **Unassign vSphere Tag** on the root vCenter Server instance
* **Content Library.Create subscribed library** or **Content Library.Create local library**
* **Datastore.Allocate space** on the destination datastore

For additional details, reference [Authentication for vSphere with Kubernetes](https://docs.vmware.com/en/VMware-vSphere/7.0/vmware-vsphere-with-kubernetes/GUID-93B29112-4492-431F-958A-12323540C38D.html)

### DevOps Engineer

A DevOps engineer might be a Kubernetes developer and an application owner, a Kubernetes administrator, or combine functions of both. A DevOps engineer uses kubectl commands to deploy vSphere Pods and Tanzu Kubernetes clusters within existing namespaces on the Supervisor Cluster. Typically, a DevOps engineer does not need to be an expert on vSphere and NSX-T but has basic understanding about these technologies and the vSphere 7 with Kubernetes platform to interact with the vSphere administrators more efficiently.

Test cases involving the DevOps engineer role require at least one (1) user account. The recommendation is to create a group such as one named DevOps in the identity source and add individual user accounts as members to the group.  After enabling a vSphere cluster as a Supervisor cluster and creating a namespace, the vSphere administrator will have the ability to entitle the DevOps engineer with namespace-level permissions.  There are two types of permissions, edit and view. This test plan requires the DevOps engineer to maintain edit permissions across namespaces. With the namespace edit permission entitlement, the DevOps engineer will automatically receive cluster-admin privileges for all TKCs deployed within the namespace, respectively.

### Application Developer

Application developers translate business and product objectives into application code. They administer the application development life cycle through CI/CD pipeline automation and an assortment of product integrations. They connect to a Tanzu Kubernetes cluster and use kubectl commands or other tools such as Helm or Jenkins to deploy workloads, including pods, services, load balancers, and other resources.

Test cases involving the application developer role require at least two (2) user accounts. The recommendation is to create two (2) groups such as DevTeamA and DevTeamB in the identity source and add individual user accounts as members to the groups.  After the DevOps engineer deploys a TKC, the DevOps engineer will have the ability to entitle the application developer with permissions to the TKC through standard Kubernetes RBAC policies.

## vSphere 7 with Kubernetes PoC Test Environment

>NOTE: BEFORE PROCEEDING TO THE TEST CASES, READ THIS SECTION IN ITS ENTIRETY AS IT INCLUDES PREPARATIONS AND PREREQUISITES REQUIRED TO SUCCESSFULLY RUN THE TEST CASES.

The test cases within this document assume that the installation of vSphere 7 with Kubernetes and NSX-T are complete and deployed to an infrastructure prepared according to the requirements detailed in the "VMware vSphere 7 with Kubernetes PoC Prerequisites and Preparations Guide." Additionally, it assumes that the Customer engaged with a VMware Systems Engineer for the vSphere 7 with Kubernetes PoC design and installation.  The following subsections identify the environment expectations, software and tools required for effectively conducting the test and evaluation process.

### VMware Software Build Information

For the deployed vSphere 7 with Kubernetes PoC environment, populate the following table with the system components’ version and build number.

Software Product | Version | Build
--- | --- | --- |
VMware vSphere ESXi | 7.0.0 | 15843807 |
VMware vCenter | 7.0.0 | 15952599 |
VMware NSX-T | 3.0.0 | 15946738 |
vRealize Operations Manager |   |   |
vRealize LogInsight |   |   |

### Software Test Tools

The recommendation for executing the test procedures is to represent the vSphere Administrator, DevOps Engineers, and Application Developer clients with individual machines (physical or VM). Alternatively, one client machine is acceptable; however, the user should expect to routinely log-in and log-out of sessions, manage multiple kubeconfig files, or repeatedly clear kubeconfig. Regardless, the table below identifies the software utilities required for each machine, respectively.

S/W Tool | Admin | DevOps | AppDev |
:-- | :-: | :-: | :-: |
OS | Rec: Ubuntu<br>Alt: Any | Rec: Ubuntu<br>Alt: Any | Rec: Ubuntu<br>Alt: Any |
Text Editor | Rec: Visual Studio Code | Rec: Visual Studio Code | Rec: Visual Studio Code |
Docker CE |    |  X  |   |
Helm 3 |    |  X  |   |
curl |  X  |  X  |   |
jq |  X  |  X  |   |
wget |  X  |  X  |   |
OpenSSL |  X  |  X  |   |
SSH Client |  X  |  X  |   |
Git |  X  |  X  |   |
JMeter |    |  X  |   |

### Test Code Repository

The test case templates are available to view on [GitHub](https://github.com/ModernAppsNinja/v7k8s-tc-templates.git).  Executing the test procedures requires locally stored copies of the repository to exist on both the Operator and Developer VMs or workstations. Clone the repository to the test users’ console with command

```
git clone https://github.com/ModernAppsNinja/v7k8s-tc-templates.git 
```

or download the .zip package. Unless specified otherwise, the test case procedures in this document assume that the tester’s present working directory is

<pre>/<i><b>PATH</i></b>/v7k8s-tc-templates/</pre>

### Test VM Images

To demonstrate the integration of the traditional VM-based workload and containerized applications, test case SC02-TC10 requires an Ubuntu virtual machine. Download the base .iso image from: https://www.ubuntu.com/download/server

### Test Container Images

Many test cases run container images for demonstrating sample application deployments. The prerequisites section for each test case identifies the required container images and paths to obtain them from a public repository. By default, the test cases assume that the worker nodes have access to the public Internet, either directly or via a web proxy configured in vSphere 7 with Kubernetes, to pull the images.  However, not all environments permit communication flows between the Kubernetes components and the Public Internet.  In this situation, the container images need to be manually built or pulled to a client workstation, tagged, and then pushed to a private registry such as Harbor. See section 2.3.4.1 for OS-specific instructions on configuring the docker client to interact with Harbor and the Notary service. Additionally, before issuing commands such as kubectl apply, kubectl run, or helm install, the tester needs to review each application spec or values file and update the image source with the private registry path and if necessary ImagePullSecrets.

The table below contains an inventory of all container images used throughout this plan so that tester can download, tag, and push the images to a private registry in advance of the actual test date.  

Test Case | Image
--- | --- 
[sc06-tc02](./sc06/sc06-tc02.md) |  jenkins/jenkins
[sc06-tc02](./sc06/sc06-tc02.md) |  jenkins/jnlp-slave
[sc02-tc05](./sc02/sc02-tc05.md) |  gcr.io/google-samples/hello-app
[sc02-tc05](./sc02/sc02-tc05.md) |  gcr.io/google-samples/hello-app
[sc02-tc05](./sc02/sc02-tc05.md) |  quay.io/kubernetes-ingress-controller/nginx-ingress-controller
[sc02-tc11](./sc02/sc02-tc11.md) |  minio/minio
[sc02-tc01](./sc02/sc02-tc01.md) |  gcr.io/google-samples/hello-app
[sc02-tc01](./sc02/sc02-tc01.md) |  gcr.io/google-samples/hello-app
[sc02-tc10](./sc02/sc02-tc10.md) |  wordpress
[sc02-tc04](./sc02/sc02-tc04.md) |  gcr.io/kubernetes-e2e-test-images/echoserver
[sc02-tc04](./sc02/sc02-tc04.md) |  quay.io/kubernetes-ingress-controller/nginx-ingress-controller
[sc02-tc09](./sc02/sc02-tc09.md) |  nginx
[sc02-tc09](./sc02/sc02-tc09.md) |  alpine
[sc02-tc08](./sc02/sc02-tc08.md) |  nginx
[sc02-tc08](./sc02/sc02-tc08.md) |  alpine
[sc02-tc03](./sc02/sc02-tc03.md) |  gcr.io/google-samples/hello-app
[sc02-tc03](./sc02/sc02-tc03.md) |  gcr.io/google-samples/hello-app
[sc02-tc03](./sc02/sc02-tc03.md) |  docker.io/projectcontour/contour
[sc02-tc03](./sc02/sc02-tc03.md) |  docker.io/projectcontour/contour
[sc02-tc03](./sc02/sc02-tc03.md) |  docker.io/envoyproxy/envoy
[sc02-tc07](./sc02/sc02-tc07.md) |   docker.io/istio/pilot
[sc02-tc07](./sc02/sc02-tc07.md) |   docker.io/istio/proxyv2
[sc02-tc07](./sc02/sc02-tc07.md) |   docker.io/jaegertracing/all-in-one
[sc02-tc07](./sc02/sc02-tc07.md) |   docker.io/prom/prometheus
[sc02-tc07](./sc02/sc02-tc07.md) |   grafana/grafana
[sc02-tc07](./sc02/sc02-tc07.md) |   istio/pilot
[sc02-tc07](./sc02/sc02-tc07.md) |   istio/proxyv2
[sc02-tc07](./sc02/sc02-tc07.md) |   jaegertracing/all-in-one
[sc02-tc07](./sc02/sc02-tc07.md) |   prom/prometheus
[sc02-tc07](./sc02/sc02-tc07.md) |   quay.io/kiali/kiali
[sc02-tc07](./sc02/sc02-tc07.md) |   docker.io/istio/examples-bookinfo-details-v1
[sc02-tc07](./sc02/sc02-tc07.md) |   docker.io/istio/examples-bookinfo-productpage-v1
[sc02-tc07](./sc02/sc02-tc07.md) |   docker.io/istio/examples-bookinfo-ratings-v1
[sc02-tc07](./sc02/sc02-tc07.md) |   docker.io/istio/examples-bookinfo-reviews-v1
[sc02-tc07](./sc02/sc02-tc07.md) |   docker.io/istio/examples-bookinfo-reviews-v2
[sc02-tc07](./sc02/sc02-tc07.md) |   docker.io/istio/examples-bookinfo-reviews-v3
[sc02-tc07](./sc02/sc02-tc07.md) |   docker.io/istio/proxyv2
[sc02-tc07](./sc02/sc02-tc07.md) |   istio/examples-bookinfo-details-v1
[sc02-tc07](./sc02/sc02-tc07.md) |   istio/examples-bookinfo-productpage-v1
[sc02-tc07](./sc02/sc02-tc07.md) |   istio/examples-bookinfo-ratings-v1
[sc02-tc07](./sc02/sc02-tc07.md) |   istio/examples-bookinfo-reviews-v1
[sc02-tc07](./sc02/sc02-tc07.md) |   istio/examples-bookinfo-reviews-v2
[sc02-tc07](./sc02/sc02-tc07.md) |   istio/examples-bookinfo-reviews-v3
[sc02-tc07](./sc02/sc02-tc07.md) |   istio/proxyv2
[sc02-tc06](./sc02/sc02-tc06.md) |  gcr.io/kubernetes-e2e-test-images/echoserver
[sc02-tc06](./sc02/sc02-tc06.md) |  quay.io/kubernetes-ingress-controller/nginx-ingress-controller
[sc02-tc02](./sc02/sc02-tc02.md) |  nginxdemos/hello
[sc04-tc05](./sc04/sc04-tc05.md) |  k8s.gcr.io/redis
[sc04-tc05](./sc04/sc04-tc05.md) |  gcr.io/google_samples/gb-redisslave
[sc04-tc05](./sc04/sc04-tc05.md) |  gcr.io/google-samples/gb-frontend
[sc04-tc05](./sc04/sc04-tc05.md) |  minio/minio`



### TKC Node Images – Content Library

Prior to deploying 

* For systems in environments with unrestricted [public Internet access](https://docs.vmware.com/en/VMware-vSphere/7.0/vmware-vsphere-with-kubernetes/GUID-77D01137-8C82-4477-A18E-DA935BC121BA.html)
* For systems in a [air-gapped](https://docs.vmware.com/en/VMware-vSphere/7.0/vmware-vsphere-with-kubernetes/GUID-97F9B43E-F264-46F1-8CD4-BD5FB68F8660.html) environment.

## vSphere 7 with Kubernetes PoC Test Scenarios

The test plan takes a scenario-based approach to system-level validation and functional verification. The test scenarios represent common use cases for vSphere 7 with Kubernetes in operation and involve tasks that exercise multiple system components and interfaces. Table 9 provides a description for each of the test scenarios

Scenario ID | Scenario Description |
--- | --- |
SC01| Provision, Operate, and Manage Kubernetes Clusters |
SC02| Leverage Advanced Networking, Security, and Persistent Storage Capabilities for Containerized Applications |
SC03| Monitor Health, Logging, Metrics for Operational and Performance Visibility into Kubernetes Clusters and Containerized Applications |
SC04| Automate Monitoring and Fault Recovery, Scaling-out, and Software Updates for Kubernetes Clusters with Zero downtime to Containerized Applications |
SC05| Operate a Secure Registry for Storing Applications' Container Images and Charts |
SC06| Automate the Deployment of Kubernetes Clusters and Containerized Applications with REST API and CI/CD |

Groups of test cases support each scenario with objective-based demonstration procedures and expected results. The following table lists an inventory of the scenarios’ test cases, respectively.

### Test Cases Inventory

#### SC01: Provision, Operate, and Manage Kubernetes Clusters

Test Case ID | Test Case Description |
--- | --- |
[SC01-TC01.md](sc01/sc01-tc01.md)| Enable a vSphere Cluster for Kubernetes Workloads
[SC01-TC02.md](sc01/sc01-tc02.md)| Create and Configure a Supervisor Cluster Namespace(s) with RBAC
[SC01-TC03.md](sc01/sc01-tc03.md)| Create and Configure a Supervisor Cluster Namespace(s) with Resource Limitations
[SC01-TC04.md](sc01/sc01-tc04.md)| Provision a Tanzu Kubernetes Cluster Using the Tanzu Kubernetes Grid Service
[SC01-TC05.md](sc01/sc01-tc05.md)| Apply RBAC to a Tanzu Kubernetes Grid Cluster and Granting Developer Access
[SC01-TC06.md](sc01/sc01-tc06.md)| Use Pod Security Policies with a Tanzu Kubernetes Cluster(s)
[SC01-TC07.md](sc01/sc01-tc07.md)| Manage a Tanzu Kubernetes Cluster with the Web UI (Dashboard)

#### SC02: Leverage Advanced Networking, Security, and Persistent Storage Capabilities for Containerized Applications

Test Case ID | Test Case Description |
--- | --- |
[SC02-TC01.md](sc02/sc02-tc01.md)| Ingress Controller – Layer 7 HTTP for Sample App Deployed to a Supervisor Cluster Namespace
[SC02-TC02.md](sc02/sc02-tc02.md)| Layer 4 TCP/UDP Load-balancing for a Sample App Deployed to a Tanzu Kubernetes Cluster
[SC02-TC03.md](sc02/sc02-tc03.md)| Ingress Controller (Contour) – Layer 7 HTTP for a Sample App Deployed to a Tanzu Kubernetes Cluster
[SC02-TC04.md](sc02/sc02-tc04.md)| Ingress Controller (Contour) – Layer 7 HTTPS for a Sample App Deployed to a Tanzu Kubernetes Cluster
[SC02-TC05.md](sc02/sc02-tc05.md)| Ingress Controller (NGINX) – Layer 7 HTTP for a Sample App Deployed to a Tanzu Kubernetes Cluster
[SC02-TC06.md](sc02/sc02-tc06.md)| Ingress Controller (NGINX) – Layer 7 HTTPS for a Sample App Deployed to a Tanzu Kubernetes Cluster
[SC02-TC07.md](sc02/sc02-tc07.md)| Deploy Istio Service Mesh to a Tanzu Kubernetes Cluster and Demonstrate Integration with a Sample App
[SC02-TC08.md](sc02/sc02-tc08.md)| Apply Network Policy Enforcement for a Sample App Deployed to a Supervisor Cluster Namespace
[SC02-TC09.md](sc02/sc02-tc09.md)| Apply Network Policy Enforcement for a Sample App Deployed to a Tanzu Kubernetes Cluster
[SC02-TC10.md](sc02/sc02-tc10.md)| Demonstrate Coexistence of Containerized Applications and Traditional Virtual Machines on Common Infrastructure
[SC02-TC11.md](sc02/sc02-tc11.md)| Demonstration Running Sample, Stateful Applications with Persistent Volumes on a Tanzu Kubernetes Cluster

#### SC03: Monitor Health, Logging, Metrics for Operational and Performance Visibility into Kubernetes Clusters and Containerized Applications

Test Case ID | Test Case Description |
--- | --- |
[SC03-TC02.md](sc03/sc03-tc02.md)| Register a Tanzu Kubernetes Cluster with vRealize Operations for Cluster Visibility and Health Monitoring
[SC03-TC05.md](sc03/sc03-tc05.md)| Integrate OSS Prometheus and Grafana with a Tanzu Kubernetes Cluster
[SC03-TC06.md](sc03/sc03-tc06.md)| Manage a Tanzu Kubernetes Cluster with Tanzu Mission Control

#### SC04: Automate Monitoring and Fault Recovery, Scaling-out, and Software Updates for Kubernetes Clusters with Zero downtime to Containerized Applications

Test Case ID | Test Case Description |
--- | --- |
[SC04-TC02.md](sc04/sc04-tc02.md)| Demonstrate a Self-Healing Tanzu Kubernetes Cluster
[SC04-TC03.md](sc04/sc04-tc03.md)| Demonstrate Scaling-out/in(Future) a Tanzu Kubernetes Cluster(s)
[SC04-TC05.md](sc04/sc04-tc05.md)| Use Velero to Backup and Restore a Tanzu Kubernetes Cluster(s), Apps, and Persistent Volumes
[SC04-TC07.md](sc04/sc04-tc07.md)| Destroy Tanzu Kubernetes Cluster and Related Objects

#### SC05: Operate a Secure Registry for Storing Applications’ Container Images

Test Case ID | Test Case Description |
--- | --- |
[SC05-TC01.md](sc05/sc05-tc01.md)| Enable the Embedded Private Container Registry and Integrate it with the vSphere 7 with Kubernetes Clusters
[SC05-TC02.md](sc05/sc05-tc02.md)| Demonstrate Vulnerability Scanning of Images Residing in the Container Registry
[SC05-TC03.md](sc05/sc05-tc03.md)| Demonstrate Applying Content Trust Policies to Container Registry Images
[SC05-TC04.md](sc05/sc05-tc04.md)| Deploy an App via Helm Chart to a Tanzu Kubernetes Cluster
[SC05-TC05.md](sc05/sc05-tc05.md)| Deploy an App via Helm Chart to a Tanzu Kubernetes Cluster

#### SC06 Automate the Deployment of Kubernetes Clusters and Containerized Applications with REST API and CI/CD

Test Case ID | Test Case Description |
--- | --- |
[SC06-TC01.md](sc06/sc06-tc01.md)| Execute REST API Calls to vCenter for Enabling a Supervisor Cluster and Creating a New Namespace
[SC06-TC02.md](sc06/sc06-tc02.md)| Install Jenkins to the Supervisor Cluster and Create and Execute a Jenkins Project that Deploys a Tanzu Kubernetes Cluster
[SC06-TC03.md](sc06/sc06-tc03.md)| Use Jenkins to Automate the Deployment of a Containerized App to a Tanzu Kubernetes Cluster
[SC06-TC04.md](sc06/sc06-tc04.md)| Execute an Argo CD Pipeline that Deploys an App to a Tanzu Kubernetes Cluster
