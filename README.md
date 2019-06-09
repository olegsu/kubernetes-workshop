<img src="logo.jpg">

* [Negev Web Developer](https://www.meetup.com/NegevDev)
* Link to meetup [event](https://www.meetup.com/NegevDev/events/261485537/)

## Requirements
* Tools:
    * docker, docker-for-[mac](https://docs.docker.com/docker-for-mac/install/)/[win](https://docs.docker.com/docker-for-windows/)
    * kubernetes cluster
    * [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) configured to work with the cluster
* Registred account in:
    * [dockerhub](https://hub.docker.com)
    * [github](https://github.com)

In this workshop we will go over the basics of kubernetes
* What is a container orchestration system
    * Which problems is should solve
        * Scale
        * Multi-nodes
        * Networking and service discovery
        * Deployment strategy (avoid downtime)
        * Healing and disastore recovery
        * Monitoring and alerts
        * Security
* Kubernetes
    * History
    * Architecture
    * Entity model
        * Pod
        * Deployment
        * Service
        * Namespace
        * Configmap
    * RBAC
    * APIS
    * Using the `kubectl`
        * Spin up application from yaml files
        * List all the resources created and understanding them
        * Scale one of the services
        * Delete service to see the auto healing process
        * Push new application version
        * Regression detection
        * Rollout
        * Fix and apply stable version
