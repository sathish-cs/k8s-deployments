# Kubernetes

### Deployment of a containerized stack in the cloud

I have used GKE managed cluster for this setup.


GKE Cluster creation

`
gcloud container clusters create CLUSTER_NAME --zone COMPUTE_ZONE --node-locations COMPUTE_ZONE,COMPUTE_ZONE1
`


GKE offers two types of clusters.

	* Zonal
	* Regional
* Zonal Clusters

Zonal clusters comes with single control plane in a single availablity zone. But worker nodes can span across multiple availablity zone. But its a single point of failure since control plane is running on single zone. 

* Regional Clusters

Regional clusters basically comes with multiple control planes which is running on multiple availablity zones. Even worker nodes can span multiple zones. This offers high availablity than the zonal cluster and recommendation for prodution. 

● Easy upgrade of the tools used if any

By default auto upgrade enabled on both cluster and node pools. Cluster upgradation for regional cluster is easier than zonal since its spanned across multi zones during upgrade another replica remains available but on zonal cluster control plan will not be available till upgradation complete, applications remains running but we cannot access api server for any changes on cluster. 


● Cloud provider 

Advantages of managed cluster like AWS EKS, GCP GKE etc

	* Automatic upgrades and security patches to control plane. 
	* Control planes will be running on multiple zones to provide high availablity. 
	* Complete management of control plane like monitoring and maintanence.

Disadvantages

	* We do not get much more flexiblity over the cluster management layer.
	* Cost is the huge factor compare to  self managed clusters.

● Easy to add/remove services

Easy to integreate service in cloud like load balancers, CICD pipelines, IAM for user management.

● Easy access to the cluster/servers and even to the containers (ssh) with a CLI

Managed cluster control plane is not accessible. But worker nodes and containers can be accessible.

● Access management

Using IAM and RBAC can be manage cluster access.


