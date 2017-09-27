# Working with IAM and RBAC

## Exercise

This is an exercise for 2 users to demonstrate how to grant additional users access to existing clusters in the IBM Container Service. It will cover granting an additional user view access to a cluster using the Bluemix Identity and Access Manager and then extending their access using a kubernetes RBAC (Role Based Access Control) policy to be more fine grained.

Contained within this folder are the task details and template yaml files for creating a role and role bindings

## Prereqs

This exercises makes the following assumptions

1. Both users have a valid Bluemix account and are linked to a valid Bluemix Infrastructure account
2. Both users have the bx, container-service and kubectl plugins installed and configured

## Tasks

1. User 1 create a paid cluster
2. User 2 try to view information about the newly created cluster
3. User 1 add user 2 as a Viewer of the newly created cluster using Bluemix Identity and Access Management tool

  ```
  Grant Viewer access to the IBM Bluemix Container Service instance
  Grant Auditor access to the Bluemix Organization
  ```

4. User 2 try to view information about the newly created cluster
  ```
  kubectl get pods --all-namespaces
  kubectl get secrets --all-namespaces
  ```
5. User 1 create two new namespaces
6. User 1 create an administrative role binding for user 2 on namespace 1
7. User 2 deploy an app to both namespaces, namespace 2 should fail
8. User 1 create an edit role binding for user 2 on namespace 2
9. User 2 deploy an app to namespace 2


## Useful links

[Using RBAC Authorization - Kubernetes.io](https://kubernetes.io/docs/admin/authorization/rbac/#api-overview)

[IBM Container Service - User management access](https://console.bluemix.net/docs/containers/cs_cluster.html#cs_cluster_user)

[IBM Container Service - Documentation Index](https://console.bluemix.net/docs/containers/container_index.html#container_index)
