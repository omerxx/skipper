# Skipper

### Managing live ECS clusters with yaml files - just like k8s

Adding a service to a live ECS cluster requires too many manual steps which often result in mistakes and rework.
The clusters description is already managed in a repo with CloudFormation templates that backup the structure.
Skipper would run through the projects on every change (using CI) and create new services if required.

1. Fetch clusters and services trees

1. Run through `masters` and compare findings

1. In case of a new service identified:
	* Use the given parameters to create a new service by deployting a stack
	* Retrieve listener from the matching load balancer
	* Create Route53 entries

