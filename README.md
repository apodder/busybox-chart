To test:
helm install --dry-run --debug ./busybox --set service.internalPort=8080
helm install --name ./busybox-example ./busybox --set service.type=NodePort
helm list
helm package busybox
https://s3-us-west-2.amazonaws.com/atanu-poc/helm/busybox-0.1.0.tgz
helm plugin install https://github.com/hypnoglow/helm-s3.git
helm s3 init s3://atanu-poc/helm
helm repo add mycharts s3://atanu-poc/helm

helm s3 push ./busybox-0.1.0.tgz mycharts
