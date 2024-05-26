In Kubernetes, a pod is the smallest deployable unit that can contain one or more containers. 
When you put two containers in a single pod, they share the same context and resources, which has several important implications:

### Shared Network Namespace
#### Same IP Address: 
All containers in the same pod share the same IP address. They communicate with each other using localhost.
#### Shared Ports: 
Containers in the same pod must coordinate their use of network ports to avoid conflicts.

### Shared Storage
#### Volumes: 
Containers in a pod can share storage volumes. These volumes are mounted into the filesystem of each container, allowing them to share data.

### Shared Lifecycle
#### Co-scheduling: 
All containers in a pod are scheduled together on the same node.
#### Lifecycle Management: 
The containers in a pod are managed together. If one container fails, Kubernetes can restart the entire pod.

### Use Cases
#### Sidecar Containers: 
Often used for scenarios where multiple containers need to work closely together, such as a primary container with a helper container (e.g., log shippers, proxies).
#### Init Containers: 
Special containers that run before the main containers in a pod, performing setup tasks such as initializing data or configuration.


# Accessing Containers in Kubernetes

In Kubernetes, each pod is assigned a unique IP address within the cluster, allowing containers within different pods to communicate with each other using these IPs. However, for stable access and load balancing, Kubernetes uses services.

## Cluster IP Address for Pods

- **Pod IP Address**: Each pod has a unique IP address. This IP is used for inter-pod communication within the cluster.

## Kube-Proxy and Services

- **Kube-Proxy**: Kube-proxy is a network proxy that runs on each node. It maintains network rules and handles routing of traffic between pods and services.
  
- **Service and Cluster IP**: 
  - A Kubernetes service provides a stable IP address (Cluster IP) and DNS name for a set of pods. 
  - Services enable load balancing and provide a single point of access to multiple pods.
  - When you create a service, Kubernetes assigns it a Cluster IP address. This address is used to access the service, and kube-proxy ensures that requests to the Cluster IP are forwarded to the appropriate pods.

## Example

If you have a service named `my-service` that targets a set of pods, you can access this service within the cluster using its Cluster IP:

```sh
curl http://<Cluster-IP-of-my-service>
