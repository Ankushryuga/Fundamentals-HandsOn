## Init Containers:
    => 
    When your app has dependency on several informations, then init container will load them before.
    
    1. It allows you to initialize a Pod before an application container runs 
    
    => 
    1. Always run to completion.
    2. Each init container must complete successfully before the next one starts.
    3. If it fails, the kubelet repeatedly restarts it untill it succeeds.
      3.1. Unless it's restart policy is set to never.
    4. Probes are not supported
      4.1. livenessProbe, readinessProbe, or startupProbe.

kind: Kubernetes in Docker.

## Example:
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
  labels:
    app: myapp
spec:
  containers:
    -  name: myapp-container
       image:  busybox
## Init containers
  initContainers:
    -  name: init-myservice
       image: busybox:1.28
       command: ['sh', '-c', "until nslookup mysvc.namespace.svc.cluster.local; do echo waiting for myservice; sleep 2; done"]
    -  name: init-mydb
       image:busybox:1.28
       command: ['sh', '-c', "until nslookup mydb.namespace.svc.cluster.local; do echo waiting for mydb; sleep 2; done"]
