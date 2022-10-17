## Hello-Tekton

Use a Tekton pipeline to build and deploy a simple hello world node application with IBM Cloud Devops ( https://cloud.ibm.com/devops).

The `.tekton` folder contains Tekton Resource definitions that create a Tekton PipelineRun. This "runs" a pipeline that builds a simple node application into an image, scans the image for vulnerabilities, and then deploys the application with IBM Cloud Kubernetes Service.

In order to build and deploy to your own cluster this sample requires parameterization of the following:
- `apikey` an IBM Cloud API Key
- `cluster` the name of your IKS cluster where you will be deploying the sample app
- `clusterNamespace` the namespace in your cluster where the app will be deployed (default: `prod`)
- `clusterRegion` the region where your IKS cluster is located (default: `us-south`)
- `registryNamespace` the IBM Cloud Container Registry namespace where the app image will be built and stored.
- `registryRegion` the region where your  IBM Cloud Container Registry is located (default: `us-south`)
- `repository` the source git repository where your resources are cloned (default: `https://github.com/open-toolchain/hello-tekton`). Change this if you are forking this repo
- `revision` the branch of the source git repository where your resources are cloned (default: `master`).

For more information on Tekton Pipelines wih IBM Cloud Devops visit https://cloud.ibm.com/docs/services/ContinuousDelivery?topic=ContinuousDelivery-tekton-pipelines

Note that this example targets the **0.11.2 release** of Tekton.

The other branches in this repo contain examples that target different releases. (NOTE: since the IBM Cloud CLI and the k8s versions are constantly upgrading there is no guarantee that all branches in this repo will continue to run forever. The main branch will be kept up-to-date.) 

The branches contain:

* tekton-0.7.0: targets the 0.7.0 tekton release
* tekton-0.10.1-pvc: targets the 0.10.1 tekton release, uses a pvc to pass info
* tekton-0.10.1-workspaces: targets the 0.10.1 tekton release, uses a workspace to pass info
* tekton-0.11.2: targets the 0.11.2 tekton release, uses a workspace to pass info (same as master)
* tekton-0.11.2-artifactory: same as tekton-0.11.2 + an example of how to use artifactory
