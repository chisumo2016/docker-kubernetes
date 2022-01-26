### KUBERNETES INTRODUCTION
    - Moving to another environment
    - Gonna move from docker compose  file into kubernetes

### COURSE OVERVIEW
    Kubernetes from a Developer perspective
    Creating Pods
    Creating Deployments
    Creating Services
    Understanding Storage Options
    Creating ConfigMaps  and Secrets

### MODULE OVERVIEW
    Kubernetes Overview
    The Big Picture
    Benefits and Use Cases
    Running Kubernetes Locally  
    Getting Started with Kubectl
    Web UI Dashboard

## Kubernetes Overview
    "k8s is an open source system for automating deployment, scaling, and management
        of containerized applications."
          https://kubernetes.io

## Managing the Container
    Server  ===> API ===> Redis
                 API 
                 API ===> db
    How do you manage all of these containes in test/stage/production?
    - How do you manage all of these containes in test/stage/production?
    - How are you Deploying/Managing your containers?
    - How Do You Scale and Load Balancer Vms?
    - It would Be Nice if You could
            * Package up an app , provide a manifest and let something else manage it for us
            * Not worry about management of containers
            * Eliminate single points of failures and self-heal containers
            * Have a robust way to scale and load balance containers
            * Update containers without bringing down the whole app
            * Have a robust networking and persistent storage options ,container can talk to each other.
            * Example :Take Ochestor  .The Kubernetes (conductor) - Inside the venue you will many
            containers, if once container is failed , The job of conductor is to bring it back up.
     NB:Kubernetes is the conductor -> orchestra container.

    - Docker compose isnt intended to used a production environment, across to a different environment.
    - What if we could define the containers we want and then hand it off to a system that manages it all for us?
            ## WELCOME TO KUBERNETES 
# KEY FEATURES
    - Service Discovery/Load Balancing-kubernetes.The grp of machine that working together to run our containers.
    - Storage Orchestration - As Volume
    - Automate Rollouts/Rollbacks - Deployment , we can archive by zero time deployment
    - Manage Workloads -
    - Self-Healing - Bring up container if goes down
    - Secret and Config Management
    - Horizontal Scalling - Scale up and down(memory)
    - More , networking

## The Big Picture
    - Have a MASTER - In charge of all the children
    - MASTER - This is boss 
    - worker node :Server / physical machine
    - Child  - Node (Pod) Node (Pod) Node (Pod) ,you can put mmultiple thing in the POD, Can run in multiple nodes
    - Multile node  which are managed by the master we call CLUSTER
    - Pod host the containers
    - Container and cluster management
    - OS project
    - Cloud support
    CURRENT STATE    ===> K8S ========> DESIRED STATE
    Container                           container container container    

## PODS AND CONTAINERS
    - Pod is like a box which container goes in                      
    - We can have multiple pods on Kubernetes                    
    
## Kubernetes build blocks
    Master
       Store(etcd)
       API (Yaml, JSON)
       Controller Manager
       Scheduler
    Will manage all the nodes
    Developers can use $kubectl to manage the pods
    You need the way the pods to communicate with each other
        Deployment  ==>Pod (Container)  , Pod (Container)  , Pod (Container)  
        Replicaset  ==>Pod (Container)  , Pod (Container)  , Pod (Container) 
    The communication is done by kubernetes services
    we can send Yaml/Json  to the server and it will create the pod 

## KUBERNETES NODES
    Each  nodes has additions of pods running ,we need the mechanism to communicate back
    and forward to the Master
    Based on that , we shoud install the plugin called kubelet ,to allwo to communicate with Master.
    kubelet is a plugin which is installed on all the nodes
    We need the Container runtime to run with the pod
    We need the netwoking plugin to run with the pod- kube-Proxy
    The kube-proxy makes the pods gets the unique address

### Benefits and Use Cases
      I am a developer ,why do I need to install kubernetes?
      Accelarate development as developer
      Eliminate conflicts    
      Enviroment  Consistency dev, Prod 
      Ship software Faster

### Key Kubernetes Benefits
      Orchestrate our containers
      Zero downtime deployment
      Self-healing   (superpowers) 
      Scale our containers horizontally

### Key Container Benefits
    Accelerate developer Onboarding
    Eliminate App conflicts
    Enviroment Consistency
    Ship Software Faster
 
    NOTE: The above is great but what if  the company has  decided to move to the next level ?

### Developer Use Cases and Benefits  
    Emulate production environment locally
    Move from Docker Compose to Kubernetes
    Create an end to end  test environment
    Ensure application scales properly
    Ensure security/ config properly
    Performance testing scenarios
    Workload scenarios (CI/CD)
    Learn how to leverage  deployment
    Help DevOps create resource and solvee problems

### RUNNING KUBERNETES LOCALLY
    # Installing and Running Kubernetes
        Minikube            https://github.com/kubernetes/minikube
        Docker Desktop      https://www.docker.com/products/docker-desktop 
        Kind                https://kind.sigs.k8s.io
        Kubeadm             https://kubernetes.io/docs/reference/setup-tools/kubeadm/kubeadm

        kubetcl get all

### GETTING STARTED WITH KUBECTL
    Getting Started with Kubectl Commands
        Check kubernetes version
            kubectl version
        View cluster information
            kubectl cluster-info

        Retrieve information about kubernetes Pods, Deployments, Services, and Nodes
            kubetctl get all

        Retrieve a Specific Service
            kubectl get pods
            kubectl get deployments
            kubectl get services
            kubectl get nodes 

        Simple way to create a Deployment for a Pod
            kubectl run [container-name] --image=[image-name]
            kubectl run [container-name] --image=[image-name] --port=[port-number]

        Forward a port to allow external eccess
            kubectl port-forward [pod] [port]

        Exposee a port for a Deployment/Pod 
            kubectl expose ...  

        Create a resource
            kubectl create [resource]

        Create  or modify a resource
            kubectl apply [resource]

## Aliasing kubectl (to save on typing)
 # PowerShell
    Create alias for PowerShell
        set-Alias --Name k -Value kubectl

# Mac/Linux
    Create alias for Mac/Linux  Shell
        alias k="kubectl"

### Web UI Dashboard
    Web UI Dashboard provides a user interface to view kubernetes resources
        https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/
    Steps to enable the UI Dashboard:
         kubetctl apply [dashboard-yaml-url]
         kubetctl describe secret -n kube-system 
         Locate the kuberntes.io/service-account-token and copy the token
        
     
### Summary
















