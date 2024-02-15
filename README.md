A simple example of a helm chart with a database as statefulSet.
I build this chart to run using Helm on Minikube.
I did not spend much time setting up ingresses and connectivity between apps and didn't use the actual database as I planned from the start (mostly because of time limitations and not sure that it's a thing that we are going to discuss).

reqiverments : 
- minikube
- helm

usage : 
`minikube start`
`helm install example-release .`

The app consists of two deployments for front and backend and one database. (all of them are just dumb placeholders).

what to do better:
- dont use k8s for data storage, better use RDS in the cloud.
- spend more time on app architecture, I don't like that kind of approach to using stateful apps in Kubernetes with data storage.
- use caching.

DISCLAIMER: 
I didn't do that kind of task in my daily routine and almost 99% time before I used k8s as a managed service in the cloud == and used specified resources for the datastore.
As an AWS specialist I don't like the idea of deploying apps this way, I'd like to use EKS + RDS for this kind of task, or even ECS + RDS to make it a lot simpler (you can check out my previous project, it a bit outdated but a bit more complex and looks better [here](https://github.com/aarogozin/pg-rds-terraform))
