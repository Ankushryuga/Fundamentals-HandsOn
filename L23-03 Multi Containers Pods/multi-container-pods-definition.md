## Multi-containers Pods.

    # Sidecar pattern
    => Typical pattern: Sidecar (Pod has shared filesystem).
    => App container: web server writes to log files
    => Sidecar: Sends log files to bucket.
    # Adapter pattern:
    => App container: Writes complex monitoring output.
    => Adapter: Simplifies monitoring output for service. (External monitoring services)
    # Ambassador Pattern:
    => App container: Needs a database connection
    => Ambassador: Proxies database connections (Production, Test, Local)
    
![image](https://github.com/user-attachments/assets/716c6095-97b8-4638-989e-e6f92728111a)
https://amitsharma13318.medium.com/understanding-kubernetes-multi-container-pod-patterns-and-init-containers-35f6996e17a1
