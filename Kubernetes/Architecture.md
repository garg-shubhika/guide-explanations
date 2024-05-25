# Kubernetes Architecture Overview

![k8s architecture](https://github.com/garg-shubhika/guide-explanations/assets/115157279/d22efccd-367b-4115-9bed-d708db3bf579)

*Image Source: https://mohan08p.medium.com/simplified-kubernetes-architecture-3febe12480eb*

## Kubernetes Components

  - **Control Plane**: The core component of Kubernetes responsible for managing the cluster and orchestrating workloads. It consists of several components:

  - **Master Node**: The primary node that controls the Kubernetes cluster. It manages the cluster state and orchestrates operations.
  
  - **Worker Node**: Also known as a minion, these nodes are responsible for running applications and handling workload tasks.
 
### Master Node Components
  
  - **API Server**: Exposes the Kubernetes API, which allows users and external systems to interact with the cluster.
  
  - **Scheduler**: Assigns pods to nodes based on resource availability and other constraints. It plays a critical role in optimizing cluster performance and maintaining workload balance.
  
  - **Controller Manager**: Ensures that the desired state of objects in the cluster matches the actual state.
  
  - **etcd**: A distributed key-value store that stores the cluster's configuration data and state.

### Worker Node Components

- **Kubelet**: An agent that runs on each node and is responsible for managing the pods and containers on that node. It interacts with the API server to receive instructions (e.g., starting, stopping, and monitoring pods) and ensures that the containers are running as expected.

- **Container Runtime**: The software responsible for running containers. Docker is a commonly used container runtime, but Kubernetes also supports other runtimes like containerd.

- **Kube Proxy**: Maintains network rules on each node. It handles network routing for services running in the cluster and enables communication between pods across the cluster.

### Pod

- **Pod**: The smallest deployable unit in Kubernetes, representing one or more containers that share resources such as networking and storage. Pods are scheduled onto nodes, and the containers within a pod always run on the same node.
  
## Running Applications in Kubernetes

- When running an application, such as a Java app, within a container, the appropriate runtime environment must be available.
- For example, a Java application requires the Java Runtime Environment (JRE) to execute successfully.

## Request Flow

- Requests to the Kubernetes cluster go through the following steps:

  1. **Client Request**: An external or internal client initiates a request to the Kubernetes cluster.
  
  2. **API Server**: The API server receives the request and authenticates and authorizes it.
  
  3. **Scheduler**: If the request involves creating or modifying a workload, the scheduler assigns it to an appropriate node.
  
  4. **Worker Node**: The worker node executes the requested operations, such as starting or stopping containers.
  
  5. **Pod**: The application runs within a pod, which encapsulates the container(s) and provides networking and storage resources.

### DockerShim

- **DockerShim**: DockerShim is a component used in Kubernetes that facilitates the integration between Kubernetes and Docker, specifically for container runtime management. It acts as a bridge between Kubernetes and Docker, allowing Kubernetes to interact with Docker as the container runtime.
