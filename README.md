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

```kubectl create token account-cluster-manager-fcjds```

3. **Identify Chaos Sandbox Resources:**

The following command lists resources (deployments, pods, and services) in the chaos-sandbox namespace, along with their labels, to help you understand the environment:

```kubectl get deployments,pod,svc -n chaos-sandbox --show-labels```

4. **Run Pod Kill Experiment:**

Apply the 3_pod_kill.yaml configuration file, which likely defines a Chaos Experiment to disrupt pods:

```kubectl apply -f 3_pod_kill.yaml```

5. ***Monitor Pod Status:***

View the pods in the chaos-sandbox namespace in a watch mode to observe their state changes:

```kubectl get -n chaos-sandbox po -w```

6. ***Clean Up (Optional):***

If you want to delete the Chaos Experiment named pod-kill-example in the chaos-mesh namespace:


```kubectl delete schedule pod-kill-example -n chaos-mesh```

7. ***Review Chaos Mesh Resources (Optional):***

Optionally, get an overview of services, pods, and deployments in the chaos-mesh namespace:

```kubectl get svc,pods,deployments -n chaos-mesh```


### Additional Points

The specific Chaos Experiment defined in 3_pod_kill.yaml may vary depending on your use case. Ensure the experiment aligns with your testing goals.
Consider adding more detailed explanations or comments within your Chaos Experiment definition for better understanding.
Replace account-cluster-manager-fcjds with a desired token name if you choose to create a token.
This guide assumes basic familiarity with Chaos Mesh and Kubernetes concepts. For more in-depth information, refer to the official Chaos Mesh documentation.