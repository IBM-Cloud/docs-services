---

copyright:

  years:  2018

lastupdated: "2018-09-04"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# About NeuVector Security Platform for Kubernetes
{: #gettingstarted}

NeuVector Multi-Vector Container Security Platform


As container deployments mature, the modern enterprise is racing to architect enterprise-wide container strategies for multi-cloud and on-prem platforms. These Kubernetes, Docker and OpenShift environments operate at highly automated scale with hundreds, and even thousands, of containers continuously interacting. The combination of east-west container traffic explosion, low network visibility and legacy security tools leave security teams blind and at-risk. NeuVector, the leader in Kubernetes security, delivers the first and only multi-vector container security platform with east-west traffic visibility, container protection, and host security combined in a highly integrated, automated security solution designed to enable the confident deployment of enterprise-wide container strategies.

{:shortdesc}

## Getting started

Getting Started with NeuVector

The NeuVector container security platform software is a container itself and is easily deployed using Kubernetes or any orchestration tool you are using.

Before deploying NeuVector, make sure your Kubernetes cluster (or docker hosts) are created, running and can be managed by tools such as ‘kubectl’.

Here are the general steps for getting started:

Contact NeuVector at info@neuvector.com or request the free trial from the website at https://neuvector.com.

Provide your Docker Hub account user name (create a free one if you don’t have one) hub.docker.com and NeuVector will add you to our private registry so you can pull the images.

Review the product documentation sent to you and start the deployment using the Kubernetes samples in the Deployment Examples or Production Deployment section, as follows.

1. Create a namespace for NeuVector
```
kubectl create namespace neuvector
```

2. Create a secret for pulling the images from Docker Hub. Alternatively, you can pull the images to your local registry and edit the sample yaml file accordingly.
```
kubectl create secret docker-registry regsecret -n neuvector --docker-server=https://index.docker.io/v1/ --docker-username=your-name --docker-password=your-pword --docker-email=your-email
```

3. Add the clusterrolebinding required
```
kubectl create clusterrole neuvector-binding --verb=get,list,watch --resource=nodes,pods,services,rolebindings.rbac.authorization.k8s.io,roles.rbac.authorization.k8s.io,clusterrolebindings.rbac.authorization.k8s.io,clusterroles.rbac.authorization.k8s.io
kubectl create clusterrolebinding neuvector-binding --clusterrole=neuvector-binding --serviceaccount=neuvector:default
```

4. Copy the sample yaml file to your terminal and deploy NeuVector
```
kubectl create -f neuvector.yaml
```
5. Access the console using the appropriate public IP (and port if using the NodePort service).

6. Enter the trial license file provided to you by NeuVector.

Review the documentation to explore NeuVector. For sample test applications and violation generation, refer to the Testing NeuVector section.

For complete guidance on getting started with NeuVector please go to [NeuVector Basics.](https://docs.neuvector.com:2018/){:new_window}


You can contact support@neuvector.com for assistance with deploying and managing NeuVector.

