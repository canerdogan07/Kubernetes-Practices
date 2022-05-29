This yaml manifest includes a website that echo's "Hello World!".

Includes concepts deployment, pod,replicaset, rollingUpdate strategy, readiness&liveness probes, with secret mounted as volume referring secret.yml file.

LivenessProbe(Health check) >> If the pod fails the container will be restarted.
ReadinessProbes >> If the readiness check fails, pod IP will be removed from the service.

For rollout purposes, the revision history limit is also increased(default=2).

Exposing the deployment with both LoadBalancer and NodePort.