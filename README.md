# Hello-Tekton
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

