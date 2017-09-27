## HA ops

## Exercise

This exercise takes the user through a brief introduction to how to safely work with high availability services in kubernetes while performing maintenance (e.g. upgrading worker nodes).

The example application is a basic Nginx server with an init script which delays startup to make observation of pod creation easier.

## Prereqs

This exercise makes the following assumptions

1. The user has administrative access to a running cluster

1. Cluster has at least three worker nodes

## Tasks

1. Install sample application

1. Check that three instances of the nginx deployment are running

1. If more than three nodes are available, cordon all nodes not running the nginx service (`kubectl cordon <node>`)

1. Drain one node running nginx (`kubectl drain --ignore-daemonsets <node>`)

1. Observe that one instance of nginx will be stuck `Pending` as there are no schedulable nodes available - at this point any maintenance on the node could be executed

1. Attempt to drain one of the two remaining nodes - this command will hang as kubernetes is unable to satisfy the `maxUnavailable: 1` pod disruption budget along with anti-affinity constraint on service

1. In another terminal, uncordon the originally drained node

1. Observe that kubernetes will schedule the previously `Pending` instance to the newly uncordoned node and the ongoing drain command should then be able to complete successfully
