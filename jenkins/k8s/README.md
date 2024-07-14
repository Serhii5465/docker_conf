### Note
For this deployment option, Jenkins must be installed as a [Docker container](https://hub.docker.com/r/jenkins/jenkins).Jenkins interacts with the K8S cluster using [Kubernetes](https://plugins.jenkins.io/kubernetes/) and [Kubernetes CLI](https://plugins.jenkins.io/kubernetes-cli/) plugins.

The Kubernetes plugins require creating a ServiceAccount for accessing the API server.


#### Deployment algorithm
1. chmod +x build && bash build
2. chmod +x create_config && bash create_config
3. Add the kubeconfig to Jenkins -> Credentials -> Secret file
4. Add Kubernetes cluster in the Jenkins -> Cloud section using ID credentials of from step 3
5. Use the `withKubeConfig(credentialsId: $VAR_ID_CRED)` directive in a Jenkins Scripted Pipeline