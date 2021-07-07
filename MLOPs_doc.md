# Useful MLOps Open-Source Tools

## Kubeflow
Kubeflow and its components allow you to manage almost every aspect of your ML experiments.

### What is KubeFlow?
The Kubeflow project is dedicated to making deployments of machine learning (ML) workflows on Kubernetes *simple, portable and scalable*. Our goal is not to recreate other services, but to provide a straightforward way to deploy best-of-breed open-source systems for ML to diverse infrastructures. Anywhere you are running Kubernetes, you should be able to run Kubeflow.

### Features
It provides a wide range of possibilities that make model deployment easier. 
* **Notebooks**: Kubeflow includes services to create and manage interactive Jupyter notebooks. You can customize your notebook deployment and your compute resources to suit your data science needs. Experiment with your workflows locally, then deploy them to a cloud when you're ready.
* **TensorFlow Model Training**: Kubeflow provides a custom TensorFlow training job operator that you can use to train your ML model. In particular, Kubeflow's job operator can handle distributed TensorFlow training jobs. Configure the training controller to use CPUs or GPUs and to suit various cluster sizes.
* **Model Serving**: Kubeflow supports a TensorFlow Serving container to export trained TensorFlow models to Kubernetes. Kubeflow is also integrated with Seldon Core, an open source platform for deploying machine learning models on Kubernetes, and NVIDIA Triton Inference Server for maximized GPU utilization when deploying ML/DL models at scale.
* **Pipelines**: Kubeflow Pipelines is a comprehensive solution for deploying and managing end-to-end ML workflows. Use Kubeflow Pipelines for rapid and reliable experimentation. You can schedule and compare runs, and examine detailed reports on each run.
* **Multi-framework**: Our development plans extend beyond TensorFlow. We're working hard to extend the support of PyTorch, Apache MXNet, MPI, XGBoost, Chainer, and more. We also integrate with Istio and Ambassador for ingress, Nuclio as a fast multi-purpose serverless framework, and Pachyderm for managing your data science pipelines.


## DAGsHub
DAGsHub is a web platform for data version control and collaboration for data scientists and machine learning engineers. The platform is built on DVC, an open-source version control system for machine learning projects that works seamlessly with Git
