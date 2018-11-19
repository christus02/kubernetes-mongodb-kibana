# Kubernetes Demo Application : Customer Portal using Kibana and mongoDB

This is the demo application for kubernetes comprising of mongoDB, elastic search, kibana and frontend application.

The landing page has a customer portal form, which upon successfull completion, the data would be stored into mongoDB.

The data in the mongoDB would be pushed to elastic search on every write using a python parser.
This data in elastic search can now be visualized in Kibana.

#Application Architecture Overview:


<img src="https://raw.githubusercontent.com/christus02/kubernetes-mongodb-kibana/master/images/app-work-flow.png" width="500">

<img src="https://raw.githubusercontent.com/christus02/kubernetes-mongodb-kibana/master/images/app-pod.png" width="500">

Please note that the python parser is basic data parser to fetch data from mongoDB and dump it into the elastic search for Kibana to be consumed. 

It was developed for demo purpose and has lots of scope for development

#How to deploy this Application

###Pre-requisites:
1. An already up and running kubernetes cluster
2. Elastic search container requires that the virtual memory to be more on the host machine on which it is running. This is a limitation with Elastic search in docker world. You can Google more about this. To overcome this limitation, execute the below command on all the worker nodes
```
sysctl -w vm.max_map_count=262144
```
3. Elastic search and MongoDB would require Persistent Volume Claims (PVC). Make sure you have necessary permissions for that.

## Deployment Steps:

You can just execute the below command to deploy the complete application

```
kubectl create -f https://raw.githubusercontent.com/christus02/kubernetes-mongodb-kibana/master/manifests/deployment.yml
```

or you can clone the repository and execute the below command

```
kubectl create -f manifests/deployment.yml
```

