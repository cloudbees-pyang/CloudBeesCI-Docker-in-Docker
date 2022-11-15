# How to configure a Pod Template to support docker-in-docker

## Steps

1. Name the container name as "jnlp";
2. Specify the container image as: https://hub.docker.com/r/jenkins/jnlp-agent-docker
3. Mount a hostpath volume, with both host path and mount path set to "/var/run"
4. Set "Run as User ID" to 0
5. To enable Jenkins user to create Kubernetes objects: kubectl create clusterrolebinding jenkinsrolebinding - -clusterrole=cluster-admin - - group=system:serviceaccounts:jenkins

## note
An image with more useful tools for pod template: https://hub.docker.com/repository/docker/poseidon1979/jnlp-agent-docker-kubectl-helm

## Alternative Solution: Kaniko
https://docs.cloudbees.com/docs/cloudbees-ci-kb/latest/cloudbees-ci-on-modern-cloud-platforms/how-to-build-my-own-docker-images-in-cloudbees-core-on-modern-cloud-platforms

