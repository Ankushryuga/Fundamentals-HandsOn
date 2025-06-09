## Selectors:
    => selectors use labels to filter or select objects.

## Labels:
    => key-value pairs used to identify, describe and group related sets of objects or resources.
      example:
      
      apiVersion:v1
      kind: Pod
      metadata:
        name: myapp-pod
        labels:
          app: myapp
          type: font-end
      spec:
        containers:
          -name: nginx-container
           image: nginx
        # Selectors:
        nodeSelector:
          disktype: superfast
