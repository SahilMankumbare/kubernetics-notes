kubernetics commands:

dry-run which will create a default file:

kubectl run redis --image=redis123 --dry-run=client -o yamal > redis-definition.yaml

output will be:
controlplane ~ ✖ cat redis-definition.yaml
apiVersion: v1
kind: Pod
metadata:
  labels:
    run: redis
  name: redis
spec:
  containers:
  - image: redis123
    name: redis
    resources: {}
  dnsPolicy: ClusterFirst
  restartPolicy: Always
status: {}