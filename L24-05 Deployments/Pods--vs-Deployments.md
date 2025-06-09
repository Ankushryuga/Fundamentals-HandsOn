## Pods vs Deployments:
    => Pods don't
    1. Self-heal: if a pod dies then k8s will not replace it
    2. Scale: only 1 instance will be created
    3. Updates: no updates available
    4. Rollback: no rollback available

    => Deployments: 
    1. Deployement manages a single pod template
    2. You create a deployment for each microservice.
      2.1. front-end
      2.2. back-end
      2.3. image-processor
      2.4. credicard-processor


## Deployments: 
      => it creates ReplicaSets in the background.
      => Don't interact with the ReplicaSet directly.


    

    
