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



‐--------------------------------------

kubectl get svc -n marketing 
kubectl get pods -n <namespace>

kubectl get svc --all-namespaces

--------------—-----------------------

the FQDN for a service is : 

<service-name>.<namespace>.svc.cluster.local


---------------------------------------------

imperative vs declarative 

imperative: means specifying commands to perform actions

declarative : means defining the desired end state and letting kubernetes determine how to achieve it.

-----------------------------------

imperative way to create service using pod : 

kubectl expose pod redis --port=6379 --name=redis-service --type=ClusterIP 

-------------------------------------------