Azure Kubernetes Service (AKS) provides a managed Kubernetes service that reduces the complexity for deployment and core management tasks, including coordinating upgrades.  
AKS cluster masters are managed by the Azure platform, and you only pay for the AKS nodes that run your applications.  
AKS is built on top of the open-source Azure Kubernetes Service Engine (aks-engine).

+ **AKS Cluster**:
  + **Cluster Master** (Azure Managed)  
    Master nodes provide the core Kubernetes services and orchestration of application workloads.  
    Abstracted from user i.e no direct access. If access required, deploy own K8s cluster using aks-engine.
 
    + **kube-apiserver**  
    The API server is how the underlying **Kubernetes APIs are exposed**. This component provides the interaction for management tools, such as kubectl or the Kubernetes dashboard.
    
    + **etcd**  
    To maintain the state of your Kubernetes cluster and configuration, the highly available etcd is a **key value store** within Kubernetes.
    
    + **kube-scheduler**  
    When you create or scale applications, the Scheduler **determines what nodes can run the workload** and starts them.
    
    + **kube-controller-manager**  
    The Controller Manager **oversees a number of smaller Controllers** that perform actions such as replicating pods and handling node operations. 

+ **Nodes**:  
  Run your **application workloads on Azure virtual machine (VM)** that runs the **Kubernetes node components and container runtime**.
  
  + **kubelet**  
  Kubernetes agent that processes the **orchestration requests from the cluster master** and scheduling of running the requested containers.
  
  + **kube-proxy**  
  Virtual networking is handled by the kube-proxy on each node. The proxy routes network traffic and manages IP addressing for services and pods.
  
  + **container runtime**  
  component that allows containerized applications to run and interact with additional resources such as the virtual network and storage. In AKS, **Moby** is used as the container runtime.

+ **Node Pools**:  
  Nodes of the same configuration are grouped together into node pools .
  
+ **Node Selectors**:  
  Let you define various parameters, such as the node OS, to **control where a pod should be scheduled**.
  
+ **Pods**:  
  represents a single instance of your application. It is a logical resource but container(s) are where the app workloads run.
  
+ **Deployments**:  
  defines the number of replicas (pods) to create.You can update deployments to **change the configuration** of pods, container image used, or attached storage.  
  **Deployment Controller uses** the Kubernetes Scheduler to run a given number of replicas on any available node with available resources
  
+ **Pod Disruption Budgets**:  
defines how many replicas in a deployment can be taken down during an update or node upgrade. For example, if you have 5 replicas in your deployment, you can define a pod disruption of 4 to only permit one replica from being deleted/rescheduled at a time.

+ **HELM**:  
Helm charts contain a packaged version of application code and Kubernetes YAML manifests to deploy resources.  
To use Helm, a **server** component called **Tiller** (manages the installation of charts) is installed in your Kubernetes cluster.  
The Helm **client** itself is installed locally on your computer, or can be used within the Azure Cloud Shell.
