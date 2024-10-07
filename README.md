# **Cloud Ran Challenge**

This repo contains the two parts of the challenge

## **Part 1: Kubernetes YAML Deployment**
- **Files**: 
  1. `deployment.yaml`
  2. `service.yaml`
- **Instructions**:
  ```bash
  kubectl apply -f deployment.yaml
  kubectl apply -f service.yaml
  ```

## **Part 2: Helm Deployment**
- **Location**: `helm/hello-app-chart/`
- **Instructions**:
  ```bash
  cd helm/hello-app-chart
  helm install hello-app .
  ```



### Overview 
For this challenge, I set up a Kubernetes environment, deployed a sample "Hello App," exposed it for testing, and packaged it with Helm for easy redeployment. 

### Environment Setup:
I chose Docker Desktop for setting up the Kubernetes environment, which offers easy integration and testing locally.

### Steps I Went Through
***
### Software Setup
- Enabled kubernetes in Docker Desktop
***


1. First created the documentation yaml file, going through the documentation page: https://kubernetes.io/docs/concepts/workloads/controllers/deployment/ which contains all the documentation and sample code that I needed to get started
2. Next, create the service yaml file, going through the documentation page https://kubernetes.io/docs/concepts/services-networking/service/ which again contains all the documentation which again contains sample code to get started 
3. All the documentation includes the fields and parameters along with what each does. 
4. Apply both yaml files via `kubectl apply -f name_of_the_file`
5. Then run `kubectl get services` to find and see the service details
6. Then `curl http://localhost:8080` to test the service. This verified that the service was accessible and functioning correctly.


### Helm Part

1. Run `helm create hello-app` to create the helm application
2. Now helm runs based off of Helm's templating syntax which basically means that we have reuse the same deployment and service file but we files to replace any hardcoded values with Helm template functions and update port numbers and more specific values
3. The run `helm install hello-app ./hello-app` to create the helm application
