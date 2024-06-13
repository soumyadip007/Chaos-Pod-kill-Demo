# Chaos Mesh Experimentation Guide

This guide provides step-by-step instructions for setting up a Chaos Mesh environment, running pod kill experiments within a designated namespace (chaos-sandbox), and monitoring the results.

## Prerequisites

* A Kubernetes cluster with Chaos Mesh installed and configured
* `kubectl` command-line tool configured with access to your cluster

## Steps

1. **Port Forwarding (Optional):**

   If you want to access the Chaos Dashboard from your local machine, execute the following command:

   ```bash
   kubectl port-forward -n chaos-mesh svc/chaos-dashboard 9090:2333 9091:2334
   ```

2. **Create a Token (Optional):**

If you need a temporary token for authentication within the scripts, run:

```
kubectl create token account-cluster-manager-fcjds
```

3. **Identify Chaos Sandbox Resources:**

The following command lists resources (deployments, pods, and services) in the chaos-sandbox namespace, along with their labels, to help you understand the environment:

```
kubectl get deployments,pod,svc -n chaos-sandbox --show-labels
```


