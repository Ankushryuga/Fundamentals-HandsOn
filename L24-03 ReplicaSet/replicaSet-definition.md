## ReplicaSets
    =>
    1. Primary method of managing pod replicas and their lifecycle to provide self-healing capabilities
    2. Their job is to always ensure the desired number of pods are running (if any of pod went down, then it will automatically add new one).


## Pod Definition:
    => 
    apiVersion: v1
    kind: Pod
    metadata:
      name: myapp-pod
      labels:
        app: nginx
        type: front-end
    spec:
      containers:
      -  name: nginx
         image: nginx:stable-alpine
         ports:
         -  containerPort: 80


## ReplicaSet Definition
      =>
        apiVersion: apps/v1
        kind: ReplicaSet
        metadata:
          name: rs-example
        spec:
          replicas: 3
          selector:
            matchLabels:
              app: nginx
              env: front-end
          template:
            <pod template>


## Final ReplicaSet Definition:
      =>
        apiVersion: apps/v1
        kind: ReplicaSet
        metadata:
          name: rs-example
        spec:
          replicas: 3
          selector:
            app: nginx
            type: front-end
          template:
            metadata:
              labels:
                app: nginx
                type: front-end
            spec:
              containers:
              - name: nginx
                image: nginx:stable-alpine
                ports:
                -  containerPort:80
        
        
