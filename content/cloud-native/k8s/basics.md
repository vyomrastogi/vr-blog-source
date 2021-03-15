---
title: "Kubernetes"
menuTitle: Basics
weight: 1
---

### What? 
Kubernetes is a container orchestration or container management tool. 
From [K8s.io](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/), 

> Kubernetes is a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.

### Why? 
Kubernetes helps in container management and provides with a framework to support multiple features of distributed, resilient and scalable system. 

It provides support for
- load-balancing and service discovery
- various storage mount options like local, nas or public cloud offerings
- automatic deployments and rollback (_canary deployments_)
- secret and configuration managements

### How?

Main components of Kubernetes 
1. API Server
2. etcd
3. Scheduler
4. Controller
5. Container Runtime
6. kublet


### Pods

Pods are the smallest object that can be created in Kubernetes. 

Sample configuration 

```yaml
#always present
apiVersion: v1 
kind: Pod
metadata:
  name: my-pod
  labels:
    app: myapp 
    tier: backend
spec: 
  containers: 
    - name: nginx-container
      image: nginx
```