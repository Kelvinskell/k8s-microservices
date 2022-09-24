# Brief Overview
This project demonstrates how to Implement a microservices architecture for an application using python, kubernetes and helm.
 This project implements a kubernetes cluster, packaged using helm.
 
 There are three total application images here:
 - `kelvinskell/newsread-extra:` A python flask web application which serves as a news contet aggregator. This particular image is a stripped down version of `kelvinskell/newsread`, which is the original flask application. Both of these images are hosted on my DockerHub repository
 - `mysql:5.7:` This is the database image used for the flask application. It is implemented in this project as a **Statefulset**.
 - `gcr.io/google-samples/hello-app`: A simple hello world image found on the Google container registry.

Essentiallly, there are two deployments: the flask application image and the hello-app image. In addition, a database is implemented as a stateful set.

This project mimics a microservices application and uses kubernetes ingress to perform path-based routing and manage traffic access to the applications.

The helm package contains everything needed to implement this application, but first, you need to provision  Kubernetes Service (EKS) cluster on your account and install theaws load balancer controller - on your AWS account.

## How To Use
**Step 1:** Create an EKS cluster on your account
**Step 2:** If not present, create an AWS IAM Open ID Connect (OIDC) for your cluster. Here is a great instruction manual on how to get that done.
