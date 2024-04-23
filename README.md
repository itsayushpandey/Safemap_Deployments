# Kubernetes Deployment files for Safemap_Deployments

On deploying deployments and services yaml files on Kubernetes Cluster in Google Cloud Platform, we can see all the pods are running and the frontend can be accessed on the External API given in below image.

![Screenshot 2024-04-23 112601](https://github.com/itsayushpandey/Safemap_Deployments/assets/32012449/116494df-6db3-4c89-a60c-68bf7e652499)

Roll outs assume there is a working K8 cluster. 

## How to setup GKE prior to deployment

1. Creating a cluster using GKE can be done by issuing the following gcloud commands:
gcloud config set compute/zone us-central1-b
gcloud container clusters create mykube --preemptible --release-channel None --zone us-central1-b

2. For gcloud authentication API we need to install auth plugin:

sudo apt-get install google-cloud-sdk-gke-gcloud-auth-plugin
3. Then do:

gcloud container clusters get-credentials mykube --region us-central1-b

4.  Setup Ingress rules by deploying the ingress:

kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.0.4/deploy/static/provider/cloud/deploy.yaml


   
