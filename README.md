# Templeate For Deploy Kubernetes Infrastructure

This is a standard template to deploy a kubernetes infrastructure in our clusters of kubernetes.

To use this template you must have installed **kustomize**.

This architecture is based on install infrastrcture of your system, all in one repository (monorepoo) or with posibility of divide in some enviroments in each repository (multirepo). **The idea is one scalable architecture**.

![Architecture to deploy k8s infrastructure.](https://drive.google.com/uc?export=download&id=1ZKcZnYBRgZLQptLF6ygxjIASTpdYBtmX)

The architecture is simple, in the folder "infrastructure" must put all your objects' kubernetes like deployment, deamonset, or statefulset of your system that you want replicate in each enviroment that you want to deploy (also of them service objects).

Then, into of folder "env" you can create all your respective enviroments that you want. In each enviroment, you can configurate all your kubernetes object for this enviroment specificly like namespace, configmaps, secrets, ingress, etc.

All this, is possible thanks that we are using kustomize as deploy tool.

For exectue an deploy on kustomize remember to use the command -k, for example:

` kubectl apply -k env/$env`
